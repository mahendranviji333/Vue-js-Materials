
server {
    gzip on;
    gzip_vary on;
    gzip_proxied any;
    gzip_comp_level 7;
    gzip_buffers 16 8k;
    gzip_http_version 1.1;
    gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

    server_name lots.learn.online;
    root /var/www/html/outreach;
    index index.html;
    location / {
            try_files $uri $uri/ /index.html;
    }

}
