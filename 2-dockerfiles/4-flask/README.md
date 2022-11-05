# Dockerizing a Flask app

## virtualenv

- [virtualenv](https://virtualenv.pypa.io/en/latest/) is a better version of [venv](https://docs.python.org/3/library/venv.html)
- Install **virtualenv** as explained [here](https://virtualenv.pypa.io/en/latest/installation.html), or:  
**sudo apt install python-virtualenv**
- Create a local virtual environment called myvenv here:  
**virtualenv myvenv**
- Activate the new virtual environment:  
**source myvenv/bin/activate**

## Flask

- install Flask:  
**pip install Flask**  
(this will install flask on your local environment)
- You can now run the app by:  
**python view.py**  
or from the IDE
- Browse to localhost:5000 to see the app output

## Dockerize the app

- run **pip freeze > requirements.txt**  
(note that we could save this file in git - to really freeze out dependencies versions)
- Build a docker image in the current directory:  
**docker build . -t myflask**
- Run the container (detached), exposing the port:  
**docker run -d -p 5000:5000 myflask**