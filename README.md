


The original Catalog web app has now been launched on an amazon lightsail server using Ubuntu, Apache2, and several python packages including Flask, SQLAlchemy, etc.<br>

### The site can be accessed with the URI:<br> 
http://18.216.143.250.nip.io/catalog

The site connects through standard port 80.

### Why the "nip.io"?
According to GoogleAPIs:
> "Authorized redirect URIs: 
For use with requests from a web server. This is the path in your application that users are redirected to after they have authenticated with Google. The path will be appended with the authorization code for access. Must have a protocol. Cannot contain URL fragments or relative paths. Cannot be a public IP address."

Connecting to the server using simply its public IP address is not allowed. Nip.io is a nifty site which maps any IP Address to a "wildcard" DNS. See <a href="http://nip.io/">Nip.io</a>. Now we can successfully use Google's OAuth2 service. Note: this is not ideal for true production applications, this is simply a work around to provide simple and easy access to Google's third party API without jumping trough the hoops for registering a true DNS.

### SSH access through port 22 has been disabled!
In order to access the server, you must use port "2200".
The ssh key for a user "grader" has been provided. In order to access the server as "grader" you can enter the following in the command line:

> ssh grader@18.216.143.250 -p 2200 -i path-to-grader-ssh-key

(where "path-to-grader-ssh-key" is the absolute or relative directory path to the ssh key contained within this repository"

### Requirements
<a href="https://github.com/JPatrick9793/Udacity_Catalog_2_Ubuntu">Here</a> is a link to the modified Catalog repository, located on the server. This repo contains all of the htm and css templates, as well as the python files used to run the server.

This repo also contains the necessary requirements.txt file which has all of the packages used in this app. Here is a link to the <a href="https://github.com/JPatrick9793/Udacity_Catalog_2_Ubuntu/blob/master/requirements.txt" target="_blank">requirements.txt</a> file contained within the aforementioned repo.

### Third-Party Resources
* [Here](http://www.bogotobogo.com/python/Flask/Python_Flask_HelloWorld_App_with_Apache_WSGI_Ubuntu14.php) Is a nice article by K Hong where he configures an apache2 server to run a simple Flask app which just outputs "Hello, Flask!".
* [Here](http://flask.pocoo.org/docs/0.12/") Here is a link to Flask's documentation
* [Here](http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/) is a link to the specific section of the Flask documentation which refers to deploying using \*mod_wsgi\*.
* [Here](https://realpython.com/blog/python/flask-by-example-part-2-postgres-sqlalchemy-and-alembic/) is an article by RealPython which walks through setting up a Flask app that calculates word-frequency pairs based on the text from a given URL.
* [Here](http://flask-sqlalchemy.pocoo.org/2.3/) is a link to the Documentation for Flsk-SQLAlchemy, which is a nice package included with Flask that simplifies sessions and querying. This helps with the problem of multi-threading, which apache2 \*mod_wsgi\* includes by default.
