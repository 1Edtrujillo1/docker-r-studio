![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/vladdsm/docker-r-studio.svg)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/vladdsm/docker-r-studio.svg)

# docker-r-studio

 R-studio in a container

 ## Description

 To allow usage of R-Studio in a portable way using Docker Container

## Container

### Run Container

`docker run --rm -p 8787:8787 -e USER=user -e PASSWORD=pasword -v <local path>:/home/user/docker_folder`

- make sure to use your own [strong] passwords in case it will work in the server.
- Remember to map correctly the folders. All working projects will be synchronised to the local computer in the folder.

### Stop Container

`CTRL + C`

### Access to a Container

1. See the container ID `docker container ls`
2. Execute the line `docker container exec -it <docker name> bash` or `docker container exec -it <docker ID> bash`, now you can see what is inside the container and make manipulations.
3. Type `exit` to go out of the container.

## Image

### Build the image

`docker login`  - to authenticate
`docker build . -t name_image:latest` - to create image

### Push to Docker Hub

1. We need to make sure that we are log-in so we type `docker login`.

2. Then we make a copy of our image `docker tag <image name>:<tag> user_name_docker_hub/<image name>:<tag>`

3. Then we push the image `docker push user_name_docker_hub/<image name>:<tag>`

### Save image locally into the archive

1. Use the command `docker save <image_name> > <image_name.tar>`
   
2. Make sure you are in the correct path.

### Delete an image

`docker image rm <name-image>` or `docker image rm <tag>`

### Restore an image

- This is useful when you want to *pull an image* from your archieve

`docker load --input <name.tar>`

### Change state of the image

1. `docker tag <name image> <name image>:Version<number>` to make a copy of the image and adding its version in the *tag*.

2. `docker image ls` check if it was copied the image.

3. Then we push the image.

- This is useful when we want to have different versions of an image.

### Modify image locally

1. Make changes in the docker file in the localhost. 

2. Be sure you are in the correct folder on the command prompt.

3. Commit the changes `docker commit -m "message" <container ID> image`

4.  Then we push the image. 

### Pull an image

1. We need to make sure that we are log-in so we type `docker login`.

2. Then we pull the image `docker pull <image name>`

