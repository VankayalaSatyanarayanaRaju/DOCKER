![alt text]({F8001310-5D8B-4BBA-975C-3A546CE9CBC3}.png)

Then if we build replicas then we will have 3 replicas with same name it cant be done remove it so it will create name on own 

now port is also the same for 3 replicas so now remove the port means just eg:8081:80 --> 80 should be there (or) 8081-8083:80

now it will create --> docker-commpose up -d

Then use docker ps --> we can see names and port numbers also

We can give replication only for application replication(compose,stack,swarm)
For database --> replication will not work

![alt text]({6A87FF73-4653-4951-9A00-345359D8690C}.png)

Reverse Proxy --> To distribute the load 

we should use single DB to overcome above conflit
![alt text]({B2AF6DA3-209F-4678-A0A2-97D0C08E1243}.png)


