Docker

========================

- What is Docker?
- Why choose Docker?
- How it is used and this difference from Virtual Machines?
- Some Docker commands
- Some best practice to write a docker file: http://docs.docker.com/articles/dockerfile_best-practices/
- Docker client
- Docker repository
- Demo
  - Login Repository:  
  ```
   sudo docker login
  ```
  - Dockerize application
    - An Interactive Container
    ```
    sudo docker run ubuntu:14.04 /bin/echo 'Hello world'
    
    sudo docker run -d ubuntu:14.04 /bin/sh -c "while true; do echo hello world; sleep 1; done"
    sudo docker ps
    sudo docker logs -f insane_babbage
    ```
  - Build docker image
  - Create docker containter
  - Run on browser
  - Link docker container https://docs.docker.com/userguide/dockerlinks/
  -  
  
