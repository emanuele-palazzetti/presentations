## Speed up your Django app with Jython and SPDY
Emanuele Palazzetti :: evonove.it
<f class="icon-twitter"></f> @palazzem



## Perché?


### Sono cambiate le nostre esigenze...

![Bootstrap](/img/bootstrap.png)
![AngularJS](/img/angularjs.png)
![EmberJS](/img/emberjs.png)


### ...e continueranno a cambiare

* Web components
* Polymer
* ECMAScript 6
* ...



### ...**eppure** HTTP/1.1 ('99)...



### Django + SPDY = (?)


![Jetty](/img/jetty.png)


![Pasta](/img/pasta-fruit.jpg)


### Jetty
* Web server e `javax.servlet` container
* Supporto per `Web sockets`
* ... diverse integrazioni con componenti Java ...
* Supporto allo stato dell'arte per **SPDY/2** e **SPDY/3**


### Jetty è un web container **Java**
*Obiettivo: eseguire una Django app dentro Jetty... ?!?*



![Jython](/img/jython.jpg)


### Jython
* `2.5.3 stable` sufficiente per Django 1.4.5
* `2.7 beta1` necessario per Django 1.5.1


### Django + Jython + Jetty + SPDY = (?)
*Bonus track: combinare SPDY con la funzionalità server push*



### Mi sto dimenticando qualcosa?

*I backend!!!*


#### Possiamo utilizzare la Django app `django-jython` (doj)

* driver zxJDBC per alcuni backend
* tool di pacchettizzazione del `WAR` per il deploy


#### Configurazione del backend

	DATABASES = {
		'default': {
			'ENGINE': 'django.db.backends.postgresql_psycopg2',
			'NAME': 'mydatabase',
			'USER': 'foo',
			'PASSWORD': 'bar',
			'HOST': 'db.example.com',
			'PORT': '',
		}
	}


#### Django-jython

	DATABASES = {
		'default': {
			'ENGINE': 'django.db.backends.postgresql_psycopg2',
			'NAME': 'mydatabase',
			'USER': 'foo',
			'PASSWORD': 'bar',
			'HOST': 'db.example.com',
			'PORT': '',
		}
	}
-

	DATABASES = {
		'default': {
			'ENGINE': 'doj.backends.zxjdbc.postgresql',
			'NAME': 'mydatabase',
			'USER': 'foo',
			'PASSWORD': 'bar',
			'HOST': 'db.example.com',
			'PORT': '',
		}
	}




### Riassunto degli ingredienti

* Django 1.4.5
* django-jython
* Jython 2.5.3 stable
* Jetty 8.1.10.v20130312 stable
* SPDY/3



![Before](/img/before_test.jpg)


![After](/img/after_test.jpg)



### Django + SPDY
### =
## BLAZING FAST!


### Obiettivi
* Django può beneficiare di implementazioni che offrono **SPDY**
* Sperimentiamo: *usiamo SPDY se possibile!*  

<br/>
<br/>

### Prossimi passi
* Utilizzare Jetty come proxy e Django + WSGI server
* Disporre di un WSGI server che supporti **nativamente** SPDY/3



### Emanuele Palazzetti

---

<f class="icon-twitter"></f> @palazzem
<f class="icon-globe"></f> evonove.it/authors/palazzem
<f class="icon-github"></f> github.com/evonove/django-spdy