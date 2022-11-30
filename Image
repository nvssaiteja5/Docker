
# DOCKER IMAGE  MANAGEMENT




## Image registry
* Images are stored in an image repository  known as image registry
* Default public registry where all images are stored is **docker hub**
* In docker hub we can either store images as public image( which everyone can access )or private images ( which only the user and his group can access)
* We can create our own images and push to docker hub



#### Docker trusted registry service
* Docker trusted registry service helps us to create our own version of docker registry  which we can use for organization internal purpose



* Some of the famous cloud providers have their own registry ,such as
(i) Google Container Registry
(ii) Amazon Container Registry
(iii) Azure Container Registry




### Docker hub
* Docker hub is a image repository where we can store the images
* In docker hub images can be catogorized into three catogiries
(i)**Official images** :- These  images are owned and maintained by docker
(ii) **Verified images**:- These images are ownned and maintained by 3rd party
(iii) **User images** :- These are created by user
(Any user created images will be under this category  )




### To view images present in system

`docker image ls` or `docker images`
* To view number of images present of host


### To search a particular image in docker hub from cli
`docker seach <image-name>`
* To search a particular image.By default, docker will search for images in docker hub

`Input: docker search <image-name>`
`output:  NAME | DESCRIPTION | STARS | OFFICIAL | AUTOMATED`
* Stars represents the popularity of the image
* Official represents whether the image is owned by the docker or not
* AUTOMATED

#### FLAGS:
##### **--limit (value)**
--limit 20 ( It only displays 20 images in cli)
* Using this flag we can specify number of images to be displayed in cli
##### example : `docker search httpd  -- limit 10`
* At max we can view 100 images in cli

#### --filter stars =10(value)
*  It only displays those images which have stars 10 or greather than 10
##### example : `docker search httpd --filter stars=10`

#### --filter is-official=true
*  It only display those images which are published by docker


##### example : `docker search httpd --filter is-official=true`

----
## Pulling and pushing an image

* We don\'t need to authenticate while pulling images from public repostiory
* To push an image into docker registry we need to authenticate first

### Pulling an image
`docker image pull (image-name):version`
* It will pull the image and store in the host system.



#### To pull an image from a particular repository:
`docker image pull (registry/user-account/image-name):version`


* If we don\'t specify the registry then docker will consider docker.io as the default one
* If we don\'t specify the user-account name then docker will consider image name as the user-acccount name by default
* If we don\t specify the version then docker will pull the image version which as the latest tag attached to it




###  Authenticating into  registry



`IP:  docker login (registry name)`
`OP: username:____`
` _   : password:_____`
* We need to pass the credentials  


### Pushing an image
* First we need to authenciate the registry
`docker image push <registry-name>/<user-name>/<image-name>`
* If we don\'t specify the registry name then it will consider docker hub as the default one


### Removing an image
* To remove an image
`docker rmi <image-name>`
* To remove an image it should not be associated with any container


### Removing all unused imges
* To remove all unsed images
`docker image prune -a`

----
### Inspecting a docker image

`docker image history <image-name>`
* We can view all layers of the image as well as the commands used to build the image

`docker image inspect <image-name>`
* It will show all  the information of the image in **json** format
* Information includes such as configuration details,ports,parent image,image size

* We can also filter the  result
`docker image inspect <image-name> -f '{{.value}}`

----
### Creating tar file from image

* In some environments we don\'t have access to the internet but we need to run a docker container of a particular image
* In such situations we will create a tar file from the image in environment which we have access to the internet (c) then we will copy to the environment and extract the image from it
Steps :
(i) Creating a tar file from image
(ii) Copy the tar file to other environment
(iii) Extracting image from tar file

##### (i) Creating a tar file from image
`docker image save <image-name> -o <file-name>.tar`
* We will get a  tar file from it

##### (ii) Copy the tar file to other environment
 * We can copy the tar file to other environment using usb or any sftp connection
 
##### (iii) Extracting image from tar file
 `docker image load -i <file-name>.tar`
* It will load the image from the tar file
----

###  Creating a tar file from the container

`docker export <container-name> > <file-name>.tar`
* It will create a tar file from the container

To extract an image from the tar file
`docker image import <file-name>.tar <image-name>`

-------


### Creating an image from container

* If we are creating a container and going into it and making some changes
* We can create an image from the container with the changes included

`docker container commit -a "message " <container-name> <image-name>`
* We need to give the container name in which we made changes


