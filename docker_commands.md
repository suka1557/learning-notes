# List of Docker commands and what they do
Create a Dockerfile and insert the following lines into it:

```docker
FROM alpine:3.15
```

This tells the docker to pull alpine base image

## To build and run containers use following commands
```bash
docker build .
```
This command will pull the Alpine Linux image version 3.15 from dockerhub.
We are using *.* in the end. So make sure that you're running the command from same folder where Dockerfile is stored

To see the docker images:
```bash
docker images
```
Here, you'll see that the Repository name and Tag are empty. It is generally a good practice to add tags when building images
So let's first remove the image using IMAGE ID with following command
```bash
docker rmi XYZ9207208
```

Let's build the image with some tags
```bash
docker build -t repository_name:tag_name .
```
Now see the image details with 
```bash
docker images
```
You'll find that now the image has a tag and a repository name

Let's push the image to our DockerHub account. To do that you must be logged into your docker account in the Docker Daemon(Desktop) running on your system.
Before pushing the image we need to assign it a tag that aligns with our Dockerhub account.

Suppose your dockerhub registry name is: docker_star

So to push the image
```bash
docker tag repository_name:tag_name docker_star/tag_name
docker push docker_star/tag_name
```

Now our goal is to run a container using the image and then interact with that container.
There are 2 ways to do it:
* Access via command line
* Or enable SSH connection via a port

It is generally not recommended to use the SSH route.

To access via the command line, we want our container to keep running a program after being built.
The way that it is configured till now, it will just pull the image and build the container and then stop. 
So to build a long running container, there should be minimum 1 ENTRYPOINT that executes a program.

To do this, change the Dockerfile as follows:
```docker
FROM alpine:3.15
RUN apk update && \
        apk add bash
ENTRYPOINT ["/bin/bash"]
```

For running the container locally use the following command:
```bash
docker build -t repository_name:tag_name .
docker run -ti -d --name alpine_test repository_name:tag_name 
```
Let's understand the flags in 2nd command:
* name: assign a custom name to the container
* ti: to allocate a TTY (emulates a terminal) and attaches stdin to it to interact with it in the terminal later
* d: run the container in the background without taking control of current terminal

Now to access the bash terminal of theis apline linux system , use the following command
```bash
docker exec -it alpine_test bash
```

This will open up the terminal of the container and you can interact with it as you like

