# Emanuele Palazzetti

.notes: These are my notes, hidden by default

# Speed up your Django app with Jython and SPDY
# evonove.it

.fx: opening-slide

---
# Django e SPDY
# Emanuele Palazzetti
# :: evonove.it

# Why?

---
# Django e SPDY
# Emanuele Palazzetti
# :: evonove.it

## Sono cambiate le nostre esigenze

<p style="text-align: center; margin-top: 20%;">
	<img alt="bootstrap" style="display: inline;" src="img/bootstrap.png">
	<img alt="angularjs" style="display: inline;" src="file:///home/palazzem/workspaces/slides-django-spdy/slides/img/angularjs.png">
	<img alt="emberjs" style="display: inline;" src="file:///home/palazzem/workspaces/slides-django-spdy/slides/img/emberjs.png">
</p>

---
# Django e SPDY
# Emanuele Palazzetti
# :: evonove.it

# ...eppure __HTTP__...

---
# Si comincia a cucinare
# Emanuele Palazzetti
# :: evonove.it

# Django + SPDY = (?)

---
# Primo ingrediente
# Emanuele Palazzetti
# :: evonove.it

<p style="text-align: center; margin-top: 20%;">
	<img alt="jetty" style="display: inline;" src="img/jetty.png">
</p>

---
# Una buona ricetta ?
# Emanuele Palazzetti
# :: evonove.it

<p style="text-align: center; margin-top: 5%;">
	<img alt="pasta" style="display: inline;" src="img/pasta-fruit.jpg">
</p>

---
# Jetty web server
# Emanuele Palazzetti
# :: evonove.it

## Cosa ci offre ?

- Web server e `javax.servlet` container
- Supporto per Web Sockets
- ... diverse  integrazioni con molti componenti Java ...
- Supporto allo _stato dell'arte_ per __SPDY/2__ e __SPDY/3__

---
# Jetty web server
# Emanuele Palazzetti
# :: evonove.it

# Jetty è un web container __Java__ #

<p style="text-align: center">
	<i>Obiettivo: eseguire una Django app dentro Jetty ... ?!</i>
</p>

---
# Secondo ingrediente
# Emanuele Palazzetti
# :: evonove.it

![jython](img/jython.jpg)

---
# Interprete Jython
# Emanuele Palazzetti
# :: evonove.it

## Jython

Versioni attualmente disponibili sono:

- `2.5.3 stable` sufficiente per __Django 1.4.5__
- `2.5.4rc1`
- `2.7beta1` necessario per __Django 1.5__

---
# La ricetta finale per Django
# Emanuele Palazzetti
# :: evonove.it

# Django + Jython + Jetty + SPDY = (?)
<p style="text-align: center">
	<i>Bonus track: supporto a SPDY con la funzionalità server push</i>
</p>

---
# Altri ingredienti ?
# Emanuele Palazzetti
# :: evonove.it

## Mi sto dimenticando qualcosa?

Non ho a disposizione i backend per i vari DATABASE

Possiamo utilizzare la Django app `django-jython` (`doj`):

- disposizione dei driver zxJDBC per alcuni backend
- tool di pacchettizzazione del `WAR` per il deploy

---
# Django - settings.py
# Emanuele Palazzetti
# :: evonove.it

## Configurazione backend di Django:

    !python
    DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'mydb',
        'USER': 'postgres',
        'PASSWORD': '123456',					# <-- No way...
        'HOST': 'db.example.com',
        'PORT': '',
	    }
	}

---
# Django - settings.py
# Emanuele Palazzetti
# :: evonove.it

## Configurazione backend di Django:

    !python
    DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'mydb',
        'USER': 'postgres',
        'PASSWORD': '123456',					# <-- No way...
        'HOST': 'db.example.com',
        'PORT': '',
	    }
	}

## Configurazione backend di Django: con `django-jython`:
	!python
	DATABASES = {
    'default': {
        'ENGINE': 'doj.backends.zxjdbc.postgresql',
        'NAME': 'mydb',
        'USER': 'postgres',
        'PASSWORD': '654321',
        'HOST': 'db.example.com',
        'PORT': '',
		}
	}

---
# Una ricetta per Django
# Emanuele Palazzetti
# :: evonove.it

## Riassunto degli ingredienti:

- Django 1.4.5
- django-jython
- Jython 2.5.3
- Jetty 8.1.10.v20130312 stable
- SPDY/3

---
# Django e SPDY: time to test!
# Emanuele Palazzetti
# :: evonove.it

<p style="text-align: center; margin-top: 5%;">
	<img alt="before" style="display: inline;" src="img/before_test.jpg">
</p>

---
# Django e SPDY: time to test!
# Emanuele Palazzetti
# :: evonove.it

<p style="text-align: center; margin-top: 5%;">
	<img alt="after" style="display: inline;" src="img/after_test.jpg">
</p>

---
# Esito della ricetta
# Emanuele Palazzetti
# :: evonove.it

# Django + SPDY = __BLAZING FAST!__

---
# Conclusioni
# Emanuele Palazzetti
# :: evonove.it

## Obiettivi

- Django può beneficiare di implementazioni che offrono l'uso di __SPDY__
- Sperimentiamo: _usiamo SPDY se possibile!_

## Prossimi passi

- Utilizzare _Jetty come proxy_ e _Django + WSGI server_
- Disporre di un WSGI server che supporti __nativamente__ SPDY

---
# Riferimenti
# Emanuele Palazzetti
# :: evonove.it

<p style="font-size:2em;">
	<b>Emanuele Palazzetti</b><br/><br/>
	e-mail: emanuele.palazzetti@evonove.it<br/>
	Twitter: @palazzem<br/>
	Source code: http://forge.evonove.it/django-spdy
</p>
