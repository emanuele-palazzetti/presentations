## Speed up your Django app with SPDY
Emanuele Palazzetti :: evonove.it
<f class="icon-twitter"></f> @palazzem



### Emanuele Palazzetti
<img src="/img/hello.gif" alt="Hello" style="width: 500px;"/>
<aside class="notes">
    Hello everyone. My name is Emanuele Palazzetti. I work as a backend software developer with django. I'm here to talk to you about SPDY protocol.<br><br>
    So what is SPDY? It's a multiplexed protocol and it does just a little thing...
</aside>



### SPDY makes the Internet faster
<img src="/img/internet_fast.gif" alt="Internet fast" style="width: 500px;"/>
<aside class="notes">
    ...it makes the Internet faster!<br><br>
    Ok, I love Python, I love Django, I could possibly love spdy, so I want to deliver my Django app over SPDY...
</aside>



### Django over SPDY? no way!
<img src="/img/no_way.gif" alt="No way" style="width: 500px;"/>
<aside class="notes">
     ...no way! At the moment there weren't any wsgi server able to support SPDY! So I did what every clever engineer would do in such situation:
</aside>



### Steal from a rich neighbor **(so evil)**
<img src="/img/stolen_tech.gif" alt="Stolen tech" style="width: 500px;"/>
<aside class="notes">
    Steal from a rich neighbor. So I take Jetty which is a pretty good Java servlet container with SPDY support at state of the art and my crazy idea was: why not run django over jython and deploy it on Jetty.<br><br>
    I didn't give .02 cents to this solution but...
</aside>



### ...it works!
<img src="/img/it_works.gif" alt="Works" style="width: 500px;"/>
<aside class="notes">
    ...it works!
</aside>



# Demo time!
(With a round trip delay of 200ms)



### So long and thanks for all the fish!

---

### Emanuele Palazzetti

<f class="icon-twitter"></f> @palazzem
<f class="icon-globe"></f> evonove.it/authors/palazzem
<f class="icon-github"></f> github.com/evonove/django-spdy
