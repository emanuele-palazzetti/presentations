### Android notifications with
### Google Cloud Messaging
![Main](/img/cloud_platform.png)

---

Emanuele Palazzetti :: Google Developer Group


### Who am I?
### Emanuele Palazzetti

---

<f class="icon-twitter"></f> @palazzem
<f class="icon-globe"></f> evonove.it/authors/palazzem
<f class="icon-github"></f> github.com/emanuele-palazzetti


### Do you know what GDG is?


Google Developer Group - Perugia
![GDG Perugia logo](/img/GDG_Perugia.png)

---

<f class="icon-twitter"></f> @GDGPerugia
<f class="icon-globe"></f> perugia.gtugs.org
<f class="icon-envelope-alt"></f> gdg-perugia@googlegroups.com



### What is Google Cloud Messaging
![GCM](/img/gcm-logo.png)


### A simple use case:
I want to chat with my friends


![Simple example](/img/useless_solutions.jpg)


![Tinker](/img/tinker.jpg)


### How will you resolve these problems?
* Store messages
* Send messages from A to B
* **Receive messages**


### Traditional **pull**?
Bad idea...too much high battery consumption


### Message push
* Request for a given transaction is initiated by a *central server*
* Clients need to register themselves to a *publisher*
* Clients are in **idle state**



![GCM](/img/gcm-logo.png)


### GCM is available for two platforms
* **Android**
* Google Chrome (extensions)


### GCM features
* Is a free Google service (no quotas)
* Helps developer send data from servers to their Android applications and upstream messages from user's device back to the cloud
* Abstraction of **all queuing problems**
* Android applications don't need to be up and running to receive messages


### More technical details
* Requires Android > 2.2 (Froyo)
* Google Play Store must be installed
* Integration with Google Play Services
* It's not required for you to deploy your app on Google Play Store
* Google account is required if Android < 4.0.4



## GCM lifecycle


### Enable GCM
Access to your API console and enable GCM for your app


### Register your app
* GCM doesn't provide anything else than a simple raw communication protocol
* You must provide an initial registration step (only the first time)
* You must have a receiving handler on your client
* You must have a sending handler on your server


## Don't worry
All API are really easy


![GCM schema](/img/GCM_schema.png)


### GCM message
* Lightweight message (max 4kb payload)
* It can be just an alert to our app (send-to-sync)
* It can contains some data on the payload (message with payload)


### Message with payload

    {
      "registration_id" : "APA91bHun4MxP5egoKMwt2KZFBaFUH-1RYqx...",
      "data" : {
        "Nick" : "Mario",
        "Text" : "great match!",
        "Room" : "PortugalVSDenmark",
      },
      ...
    }



## Some advanced features


### Suppose:
* Users of my application have more than one device
* I want to trigger a message push to all user's devices
* I don't want to query and find all device IDs


### Seamless multi-device messaging
Map a single user to a **notification_key**, which you can then use
to send a single message to multiple devices owned by the user


### Very advanced feature
1. When new contents are available on our server, we ask to GCM server to send a push message to all user's devices
2. The GCM server checks all registered devices to find the last one in active state
3. It will send the push message
4. It compare the position of this device with other user's devices and if they are too far away, the message is not delivered
    now


### Nice!

![Nice](/img/nice.gif)


### Other features
* Persistent connections
* Upstream messaging
* Synced notifications across devices



## Workshop time!


### Google AppEngine

![AppEngine](/img/app-engine.png)


![Playground](/img/google_playground_app.png)


## Be ready!
http://evo9.it/www.tofu.st/c

http://evo9.it/bradabrams.com/a



Emanuele Palazzetti :: Google Developer Group

---

<f class="icon-twitter"></f> @palazzem
<f class="icon-globe"></f> evonove.it/authors/palazzem
<f class="icon-github"></f> github.com/emanuele-palazzetti/AndroidHappyChat
