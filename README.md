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