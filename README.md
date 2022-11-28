
# Docker 

### Docker System


#####  To start docker 


`systemctl start docker`
* It  start docker daemon
* We can use the following  command  after the installation is done or when we reboot the system

`systemctl status docker`
* To check whether docker daemon is running or not 


**To stop docker completely** 
 * First we need to stop docker service 
`systemctl stop docker `  ( To stop docker service)

* Then we can stop the docker daemon service
`systemctl stop docker.socket` ( To stop docker daemon )



`dockerd`
* To run docker daemon manually in the foreground







### Docker objects

In docker we performs actions on the docker  objects and those are 

* Images
* Container
* Network
* Volumes

---

## Images
 
`docker images` or `docker image ls`
* To view the number of docker images present


`docker pull <image-name>`
* It will download image from the registry (If we don't specify the registry ,then docker will consider docker hub as the deafault registry )
---

## Containers

`docker container ps`
* To view the running containers

`docker container ps -a `
* To view all containers which includes running as well as stopped containers


`docker container ps -q`
* To get the short container id's of running container

###### Whenever we create a container.Its data is stored under **/var/lib/docker** 
### Commands to create container
`docker create <image-name>`
* It will create the container from the image which we specified but it does not start the container.
* At first, docker will look for the image in system if it does not found any image then it will pull the image from the registry (Default:dockerhub)

`docker start <id>`
* It will start the container if  either it is created or it is in stopped state


`docker run <image-name>`
* It first creates the container from the image (First container search for the image in the hosts if it doesn't found ,then it will pull the image from the registry (If we don't specify the registry, then docker will consider docker hub as the default one))
* create+start =run
* It will create the container from the image and then it starts the container





-----

### To remove a container
* To remove the container, first we need to stop it .

`docker container stop <container-name or id>`
* It will stop the container
* We can start the stopped container by using `docker start <id>` command
 

`docker container rm <container-name or id >`
* It will remove the container
* If the container is removed we cannot 

-------
#### To remove all containers

* To remove all the containers First we need to stop all container

`docker container stop $(docker container ls -q)`
* It will stop all the containers

`docker container prune`
* It will remove all the stopped containers

