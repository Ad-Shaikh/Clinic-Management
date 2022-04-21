Flask example
Using Flask to build a Restful API Server with Swagger document.

Integration with Flask-restplus, Flask-Cors, Flask-Testing, Flask-SQLalchemy,and Flask-OAuth extensions.

Extension:
Restful: Flask-restplus

SQL ORM: Flask-SQLalchemy

Testing: Flask-Testing

OAuth: Flask-OAuth

ESDAO: elasticsearch , elasticsearch-dsl

Installation
Install with pip:

$ pip install -r requirements.txt
Flask Application Structure
.
|──────app/
| |────__init__.py
| |────api/
| | |────__init__.py
| | |────cve/
| | |────user/
| | |────oauth/
| |──────config.Development.cfg
| |──────config.Production.cfg
| |──────config.Testing.cfg
| |────dao/
| |────model/
| |────oauth/
| |────util/
|──────run.py
|──────tests/

Flask Configuration
Example
app = Flask(__name__)
app.config['DEBUG'] = True
Configuring From Files
Example Usage
app = Flask(__name__ )
app.config.from_pyfile('config.Development.cfg')
cfg example

##Flask settings
DEBUG = True  # True/False
TESTING = False

##SWAGGER settings
SWAGGER_DOC_URL = '/api'

....


Builtin Configuration Values
SERVER_NAME: localhost:5000/.

JSON_SORT_KEYS : By default Flask will serialize JSON objects in a way that the keys are ordered.

reference¶
OAuth Setup
add your client_id and client_secret into config file.

ESDAO Setup
add your ES host and ES port into config file

Run Flask
Run flask for develop
$ python run.py
In flask, Default port is 5000

Run flask for production
** Run with gunicorn **

In webapp/

$ gunicorn -w 4 -b 127.0.0.1:5000 run:app

-w : number of worker
-b : Socket to bind
Run with Docker
$ docker build -t flask-example .

$ docker run -p 5000:5000 --name flask-example flask-example 
 
In image building, the webapp folder will also add into the image

Unittest
$ nosetests webapp/ --with-cov --cover-html --cover-package=app
--with-cov : test with coverage
--cover-html: coverage report in html format
Reference
Offical Website

Flask
Flask Extension
Flask restplus
Flask-SQLalchemy
Flask-OAuth
elasticsearch-dsl
gunicorn
Tutorial

Flask Overview
In Flask we trust
Wiki Page
