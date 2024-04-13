Installation:

#BuildDocker image from "Dockerfile"
docker build -t myfirstmysqlimage .

#start the container from the image that you just created
docker run -d --name myfirstmysqlconatiner -p 3412:3306 myfirstmysqlimage

Explanation:
'-d' => detached mode: means that you can close the cmd-window and the container still runs(it is detached from the cmd-window)
'--name myfirstmysqlconatiner' => specifies the name of the conatiner that will be created
'-p' maps that ports inside the container to ports outside of it; for example "insidePort:outsidePort"


#Create a network
docker network create mynetwork

#Create the mysql container
docker run -d --name mysqlcontainer --network mynetwork -p 3412:3306 mysqlimage

#Create the restApiContainer

docker run -d --name restapicontainer -p 8080:8080 -e RDS_HOSTNAME=mysqlcontainer --network mynetwork restapiimag





#not recommended to link:
#link restapiimage with mysql container "mycontainer"
docker container run -p 8080:8080 --link=mycontainer -e RDS_HOSTNAME=mycontainer restapiimage

#other usefull commands:

#remove all exited containers
docker container prune





multistage
docker compose
what about existing conatiners ? can you add them to a network ?