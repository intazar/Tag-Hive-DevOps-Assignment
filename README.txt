Taghive DevOps Assignment Steps

1. First we create Dockerfile for app_a application. 
   a. We use python base image
   b. We create a Directory "home"
   c. We copy all files like requirements.txt and app_a.py file in home directory
   d. We use RUN commnad to install 'flask' and 'requests' module from requirements.txt file
   e. We use CMD command to execute app_a.py file via python mode.
   
By using above step we create Dockerfile. Now by this Dockerfile we can create Docker Image.

Create Docker Image by Dockerfile

docker build -t imagename .
example : docker build -t taghive-app-a-img .  (By this command we create docker image)

To see docker image
docker images 

After create Docker Image we create container

docker run -itd --name container-name -p 5000:5000 imagename
example : docker run -itd --name taghive-container-first -p 5000:5000 taghive-app-a-img


To see running container
docker ps

To see running and stopped container
docker ps -a

After create container we can enter into container

docker exec -it container-name bash
example : docker exec -it taghive-container-first bash

After login container use below command to see output

curl http://127.0.0.1:5000/hello

Note : If curl command will not work so we need to install curl package in the container. 
Note : Please find "app_a Output.jpeg" pic to see output via browser. 

We find issue in app_a.py file. If we print result it should print density but in logs it shows b'density'. Please refer 'print-in-code.jpeg' & 'print-b-density.jpeg' file which I have upload in a repository.

After done dockerize concept we start task for deploy the application in Kubernetes cluster.

 a. We create deployment.yml file
 b. To access application via network we use "Servic Module" as "LoadBalancer". If we don't use this service type then we don't get access this application via URL.
 c. For High availability we use replicas as 3. It means due to some reason if one pod will not work then our application will be accessed via other pods. End user never face downtime of an application.
 
To deploy deployment.yml file we need to run below command
kubectl apply -f deployment.yml

To see all running module at we use below command
kubectl get all

By kubectl get all command we see total number of pods are running, service run  



2. For app_b application we use the same step for dockerize and deploy application on the Kubernetes as we did for app_a application

Note : I have used comment format in deployment.yml file for better understaning of flow of code.
 

Thanks & Regards
Intazarul   