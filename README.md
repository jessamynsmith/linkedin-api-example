# linkedin-api-example

Simple Flask app that connects to the Linkedin API
Original source: https://github.com/lepture/flask-oauthlib/blob/master/example/linkedin.py

### Development

Fork the project on github and git clone your fork, e.g.:

    git clone https://github.com/<username>/linked-api-example.git

Create a virtualenv using Python 3 and install dependencies. I recommend getting python3 using a package manager (homebrew on OSX), then installing [virtualenv](https://virtualenv.pypa.io/en/latest/installation.html) and [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/install.html#basic-installation) to that python. NOTE! You must change 'path/to/python3'
to be the actual path to python3 on your system.

    mkvirtualenv linked-api-example --python=/path/to/python3
    pip install -r requirements.txt
    
Create a Linkedin app:
1. Under "Default Application Permissions" select "r_basicprofile" and	"r_emailaddress".
1. Under "OAuth 2.0", "Authorized Redirect URLs", enter:
http://127.0.0.1:8000/accounts/linkedin_oauth2/login/callback/
1. Note the "Client ID" and "Client Secret"

In your clone of this app, edit linkedin.py, setting CONSUMER_KEY and CONSUMER_SECRET to the values from your Linkedin app.

Run server:

    python linkedin.py
    
If all is set up correctly, it should take you to the Linked Oauth screen, and if you authorize the Linkedin app, it will take you back to your flask site and display your profile info from Linkedin.
