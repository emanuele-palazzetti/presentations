### Feed your Android with a REST client
![Main](/img/android-eats-apple.png)

*(all references are purely coincidental)*

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



### What is Android?
![Android Terminator](/img/android_terminator.png)

It's not a killing machine...


![Android cool](/img/android_cool.jpg)

...but something very cool!


### More informations

* SDK is open source and is available for all main operative systems
* No license fees, no certification or registration required to develop your apps


### More technical details

* It's based on kernel Linux 2.6 and on 3.x from Ice Cream Sandwich version (Android > 4.0)
* API used to build the Android system are the same that are used by developers
* Almost all of basic components can be replaced with your or 3rd party application (ex: Skype, Viber, WhatsApp, etc..). There are some exception to avoid security issues
* The code is open source released as Apache License 2.0


### Android <f class="icon-heart"></f> Java

* The entire operative system and all built-in and third party apps are built with Java language
* Doesn't use standard JVM but a Dalvik VM
* It is possibile to call C/C++ code via JNI
* Kivy framework allows to write Python applications


![Android stack](/img/android_software_stack.png)


### Application layer (`Activity`)

* An Activity is an application component that provides a screen with which users can interact (dial phone, photos,...)
* Each activity is given a window in which to draw its user interface. 
* There is an Activity Stack where new activities are pushed on top
* Only one Activity at the same time can runs


![Lifecycle](/img/activity_lifecycle.png)


### Many other components

* Services
* AsyncTask
* Broadcast receivers
* Content providers
* ...



### Start speaking about workshop


### What do I want?

* I have a web service which exposes some REST APIs
* I want to build and Android application which uses these APIs


### About REST APIs

* We have resources with a global identifier (ex: URI)
* To manipulate you can use a standardized interface (ex: HTTP)
* We can use HTTP methods (GET, PUT, POST, DELETE)
* Tipically the returned information is JSON, XML, etc...


### Example

{"message": "Hello world!"}


### Our APIs (Django application)

http://students-exam.herokuapp.com/admin/
http://students-exam.herokuapp.com/api/exam/.json



### What design pattern to use?


![Wrong pattern](/img/wrong_pattern.png)


### Don't use it!


![Good pattern](/img/good_pattern.png)


![Third pattern](/img/third_pattern.png)

Another pattern...


![Foo pattern](/img/foo_pattern.gif)

...another one (a foo pattern)...


![Jackie](/img/jackie_chan.png)

...too many design patterns!


![Mind blown](/img/mind_blown.gif)

Brilliant! Why not use a library for that?!


Remember: Design patterns are really important!


### Volley library

* Used by Google inside Play Store
* Automatically schedule all network requests (even images)
* Provides transparent disk and memory caching
* Powerful cancellation request API
<br/><br/>
https://android.googlesource.com/platform/frameworks/volley



###Android distribution

http://developer.android.com/about/dashboards/index.html


### Workshop time!

https://www.tofu.st/palazzem/Android_stuff/logo_unipg.png
https://www.tofu.st/palazzem/Android_stuff/volley.zip



Emanuele Palazzetti :: Google Developer Group

---

<f class="icon-twitter"></f> @palazzem
<f class="icon-globe"></f> evonove.it/authors/palazzem
<f class="icon-github"></f> github.com/emanuele-palazzetti
