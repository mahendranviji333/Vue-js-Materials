server {
    gzip on;
    gzip_vary on;
    gzip_proxied any;
    gzip_comp_level 6;
    gzip_buffers 16 8k;
    gzip_http_version 1.1;
    gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

    server_name api.lots.learn.online;

    client_max_body_size 4G;
    types_hash_max_size 4096;

    access_log /home/django/outreach/logs/nginx-access.log;
    error_log /home/django/outreach/logs/nginx-error.log;

    location /static/ {
        alias   /home/django/outreach/static/;
    }

    location /media/ {
        add_header Access-Control-Allow-Origin *; ## this is a place some time you get Cross error for media files you need to add this one in nginx file for PDf...etc download or render issue
        alias   /home/django/outreach/media/;
    }

    # Error pages
    error_page 500 502 503 504 /500.html;
    location = /500.html {
        root /home/django/outreach/src/templates;
    }

    location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_redirect off;
        proxy_read_timeout 300s;
        proxy_connect_timeout 300s;
        proxy_request_buffering off;
        proxy_buffering off;


        if (!-f $request_filename) {
            proxy_pass http://unix:/home/django/outreach/prod/run/gunicorn.sock;
            break;
        }
    }

}
