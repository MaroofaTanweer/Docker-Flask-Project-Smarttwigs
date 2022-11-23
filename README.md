# Docker-Flask-Project-Smarttwigs
A Flask app running on Docker and Kubernetes Cluster
## OVERVIEW:

![image](https://user-images.githubusercontent.com/70618235/203452245-e6726503-1048-4aa4-91d6-7c04679731d1.png)

## Running this app
<sub3>This app is designed to run in different ways:</sub3></br>

<sub1>1. As a standalone app running on your machine</sub1></br>
<sub1>2. As a Docker container running locally and Docker image published in Docker Hub</sub1></br>
<sub1>3. As a Kubernetes Deployment running on Kubernetes Cluster</sub1></br>
## As a standalone app
<sub1>1. install python</sub1></br>
<sub1>2. clone the project form Github then change to the directory</sub1></br>
<sub1>3. run virtualenv -p /usr/bin/python3 venvor python -m venv venv to create a virtual environment</sub1></br>
<sub1>4. activate it using source venv/bin/activate</sub1></br>
<sub1>5. pip install -r requirements.txt to install the app libaries and it dependencies</sub1></br>
#### Running the app:
<sub3>After installing, run the server using python app.py . Access the running app in a browser at the URL written to the console (most likely http://localhost:5000)</sub3></br>
## Steps to deploy in Docker: 
<sub1>1. docker build -t <image_name>:tag . </sub1></br>
<sub1>1. docker image ls </sub1></br>
<sub1>2. docker run --name <container_name> -d -p ip_address:5000:5000 <image_name> </sub1></br>
<sub1>3. docker ps -a</sub1></br>
## As a Docker image published in Docker Hub
<sub4>Docker Hub is a free service to publicly store available images.</sub4></br>
<sub1> ** you need to install only Docker</sub1></br>
<sub1>1. just run:  docker run --name <container_name> -d -p ip_address:5000:5000 <image_name> </sub1></br>
<sub1>2. tag the image: docker image tag myimage:tag dockerhubrepository/myimage:tag</sub1></br>
<sub1>3. log in to DockerHub:  docker login</sub1></br>
<sub1>4. push the image to the dockerhub: docker image push dockerhubrepository/myimage:tag</sub1></br>
## As a Kubernetes Deployment running on Kubernetes Cluster
<sub1> ** you need to install Kubernetes and Configure Kubernetes Cluster</sub1></br>
<sub1>1. Create deployment: kubectl apply -f docker-flask.yaml </sub1></br>
<sub1>2. kubectl get deployment </sub1></br>
<sub1>3. Create service: kubectl apply -f docker-flask-svc.yaml </sub1></br>
<sub1>4. kubectl get svc</sub1></br>
## Troubleshooting
edit the file  /etc/docker/daemon.json and restart the docker service to resolve the error “temporary failure in name resolution')' /simple/flask/” which I got while creating docker image.
