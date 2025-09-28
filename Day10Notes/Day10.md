Docker Swarm : used to create a service and run an application on multiple servers

Docker Compose : used to run multiple services and run an application on single server

Docker Stack : swarm + compose : used to run multiple services on multiple servers


![alt text]({16028A35-2CBA-4942-89BE-F0BAB76E0437}.png)

Create 3 instances 1 Master 2 workers
Install docker in it and enable by using cmd
change hostname -->hostname set-hostname Master

Goto master install swaarm -->docker swarm init 
Paste the token in both the worker nodes

check in master how many nodes are connected --> docker node ls

Now install compose --> from all setups install docker compose 

Writing compose file --> vim compose.yml
---
version: "3"
services:
 web1:
  container_name: cont-1
  image: shaikmustafa/dm
  deploy:
   replicas: 3
  ports:
    - "8081:80"
 web2:
  container_name: cont-2
  image: shaikmustafa/cycle
  deploy:
   replicas: 3
  ports:
   - "8082:80"
---

Now to execute file we use docker stack --> docker stack deploy mystack(anyname) --compose-file=compose.yml

We can see 3 services will be created

List of services --> docker service ls
To see containers --> docker ps
Check the services of top --> docker service ps mystack_web1(ls cmd name)

we can increse the no of replicas of the stack by going to compose.yml file and change the number inc or dec. -->Then again deploy --> stack deploy mystack(anyname) --compose-file=compose.yml
(OR) docker service scale mystack_web2=6 

Try to access application using IP and port no of 8081 & 8082

To delete a stack --> docker stack rm stackName




PORTAINER --> GUI based tool 

Install portainer from all setups
ServerIP address and Portno 9000
SetUp username and password

It wont be used because of its not secure




NEW TOPIC:
Try newrelic

Select tech stack
Basic to install docker 
docker network --> default host
Save and continue
copy that thing and paste in server that we want to monitor 
Test connection
see data 
can see all the containers and workers for master
 


























build --> single server and that if for testing
Image --> we need to use in max cases