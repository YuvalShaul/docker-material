# A multi-stage Dockerfile for golang

- Using the same go program from the last example.
- You can read the comments on the Dockerfile itself.
- to build:  
**docker build . -t justrun**
- This will create 2 images:  
  - a temporary untagged image - the one that was used for the build process (a large image)
  - a small one tagged **justrun**, small, that will be used to run a container.
- to run:  
**docker run -d -p 8080:8080 justrun**
- this will:  
  - create a container running detached (so in the background)
  - will map port 8080 of the container to port 8080 of the system you are running it on
- Use your browser to **localhost:8080/something** to see the response