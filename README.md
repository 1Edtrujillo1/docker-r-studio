# docker-r-studio

 R-studio in a container

 ## Description

 To allow usage of R-Studio in a portable way using Docker Container

 ## Procedure

### Build the image

`docker login`  - to authenticate
`docker build . -t name_image:latest` - to create image

### Run Container

`docker run --rm -p 8787:8787 -e USER=user -e PASSWORD=pasword -v <local path>:/home/user/docker_folder`

### Stop Container

`CTRL + C`

### Push to Docker Hub

1. We need to make sure that we are log-in so we type `docker login`.

2. Then we make a copy of our image `docker tag <image name>:<tag> user_name_docker_hub/<image name>:<tag>`

3. Then we push the image `docker push user_name_docker_hub/<image name>:<tag>`