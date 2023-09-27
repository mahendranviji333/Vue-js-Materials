# Web push notifications using Firebase Cloud Messaging

- reference link https://blogs.halodoc.io/web-push-notification-using-firebase-cloud-messaging/

## Step 1

  1) Register service worker
       We need a service worker to send notifications. Service worker is JavaScript code that can execute in the background even if your browser is closed. In push notifications,
       the service worker manages the push events when a message is received from the server, which we will discuss later. For now, let's discuss how to register a service worker in our JavaScript code.
  2) Get user permission to send push notification
      We need to get the user's permission to send push notifications. Otherwise, we are not able to subscribe to the push service. To get user permission, we should ensure the browser supports notification API.
      Again, we can see from Caniuse that the notification API support has not yet been widely adopted. It's currently sitting at 81%.
  3) Get token from Firebase
     After the user grant permission for us to send the notification, we can fetch the Firebase registration token that can be used to send push messages to this user. We need to use Firebase SDK to get the registration token as seen in the above code snippet.
  4) Send registration token data to backend
     We need registration token as a client identifier to trigger push notifications from our backend. To send the registration token,
     we need to make a simple HTTP request to backend as seen in the above code. Then, in the backend, we need to store that subscription data in our server database:
  5) Trigger push notification requests
     We need some events to trigger the push notifications to the users. The trigger depends on the business's needs. For example, in a chat application,
     it can be a new chat notification. For e-commerce applications, the notification can be require payment. But for this example, let me create a simple endpoint to trigger push notifications:
  6) Send push request from Firebase
     Firebase's requests to push service is out of our control. But behind the scene, Firebase sends the push request to the push service. Then the push service receives the request from Firebase, authenticates it, and routes the push message to the appropriate client.
     If the client's browser is not connected to the internet, the push service queues the push message until the browser reconnects. When a browser receives a push message, it decrypts the data and sends a push event to our service worker.
  7) Receive push event from push service in the service worker
     The code for setting up a push event listener should be pretty similar to any other event listener we'd write in JavaScript:
  8) Display the push notification to the user
     
