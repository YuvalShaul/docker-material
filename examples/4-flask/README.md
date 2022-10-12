# Flask Container

##  Preparations

- Create a virtual environment inside the directory:  
**virtualenv venv**  
(this assumes you have [virtualenv](https://virtualenv.pypa.io/en/latest/index.html) installed)
- Activate yout virtual environment:  
**source venv/bin/activate**
- Install Flask:  
**pip install Flask**
- Create a requirements file:  
**pip freeze > requirements.txt**  
Explanation:  
This really freezes the versions of all python packages you have installed with pip.  
You can later install them with:  
**pip install -r requirements.txt**  
(you don't have to do that now, these are alreay installed)

## Run and test your app

- You can run your app from the command line, or from VScode, provided that you use the correct virtual environment. Otherwise, python could not find Flask:  
**python view.py**
- Browse to localhost:5000, of use curl:  
**curl localhost:5000**

## Create and run a  container

- Create an image using the Dockerfile we are using:  
**docker build -t flask_demo:0.0.1 .**  
Explanation:  
We are creating an image, and tagging it.  
Repository name: flask_demo  
tag: 0.0.1
- Use **docker images** to make sure image was created.
- Run a container from that image:  
**docker run -d -p 81:5000 flask_demo:0.0.1**
  - We use -d to run the container in a [detached mode](https://stackoverflow.com/questions/34029680/docker-detached-mode)
  - we map port 5000 of the container to port 81 of the Linux host  
    (note that port 80 is probably used by a local default http server)

## Debug

- Exec into your container:  
**docker exec -it \<container-id\> /bin/sh**
- Use **ps -e** to see processes "inside" the container
