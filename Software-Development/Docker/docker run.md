***description***:
	Run a process in a new container. *docker run* starts a process with its own file system, its own networking, and its own isolated process tree. The IMAGE which starts the process may define defaults related to the process that will be run in the container, the networking to expose, and more, but *docker run* gives final control to the operator or administrator who starts the container from the image. For that reason *docker run* has more options than any other Docker command.
	If the IMAGE is not already loaded then *docker run* will pull the IMAGE, and all image dependencies, from the repository in the same way running *docker pull IMAGE*, before it starts the container form that image.
***syntax***:
	docker run \[FLAGS\] IMAGE \[COMMAND\] \[ARG...\]
		docker run:
			the base command
		\[FLAGS\]:
			Optional flags that modify the behavior of the command.
		IMAGE:
			The name of the DOCKER image to use for creating the container
		\[COMMAND\]:
			The command to run inside the container. If a command is not specified, Docker will run the default command defined in the docker image.
		\[ARG..\]:
			Any additional arguments for the command you're running.
***flags***:
	-p
		used to publish a container's port to the host. This flag allows you to specify the port mapping between the container and the host. For example, you can use '-p 8080:80' to map port 80 from the container to port 8080 of the host.
	-d
		runs the container in detached mode, meaning it runs in the background
	-t
		allocates a pseudo-TTY, which allows you to interact with the container.
		(TTY is a text input/output environment, it allows you to interact with the container as if you were using a terminal)
	--name
		sets the container name
***example***:
	docker run -d -t --name myfirstcontainer centos
		in the example, '-d -t --name' are flags, *myfirstcontainer* is the name of the newly created container specified with '--name', and *centos* is the CentOS operating system which was specified as the image to use.