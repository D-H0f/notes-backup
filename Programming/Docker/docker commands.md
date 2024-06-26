The base command for the [[docker]] CLI is
	docker

**Options**
options you can add onto the base docker command are
	docker --config {path/to/config/file}
		the default config file is /root/.docker, and using this flag allows you to specify a custom config file
	docker -D, --debug
		enables debug mode
	docker -H, --host
		Daemon socket to connect to
	docker -l, --log-level info
		set the logging level (debug, info, warn, error, fatal)

**Subcommands**
	docker run \[FLAGS\] \[IMAGE\]
		description:
			Run a process in a new container. *docker run* starts a process with its own file system, its own networking, and its own isolated process tree. The IMAGE which starts the process may define defaults related to the process that will be run in the container, the networking to expose, and more, but *docker run* gives final control to the operator or administrator who starts the container from the image. For that reason *docker run* has more options than any other Docker command.
			If the IMAGE is not already loaded then *docker run* will pull the IMAGE, and all image dependencies, from the repository in the same way running *docker pull IMAGE*, before it starts the container form that image.
		example:
			docker run -d -t --name myfirstcontainer centos
			in the example, -d -t --name are flags, and centos is the CentOS operating system which was specified as the image to use.
		used to run a docker container, optional flags are:
			-d
				runs the container in detached mode, meaning it runs in the background
			-t
				allocates a pseudo-TTY, which allows you to interact with the container.
				(TTY is a text input/output environment, it allows you to interact with the container as if you were using a terminal)
			--name
				sets the container name
	docker ps
		lists running docker containers
	docker exec \[FLAGS\] \[CONTAINER\] \[COMMAND\] \[ARG...\]
		syntax:
			-'FLAGS': optional flags to modify the action of the 'docker exec' command.
			-'CONTAINER': The name or ID of the container where you want to run the command
			-'COMMAND': The command you want to run inside the container.
			-'ARG...': Any arguments for the command you are running.
		flags include:
			'-d', '--detach\[=false\]': Detached mode: run command in the background
			'-e', '--env=': set environment variables.
			'--env-file=': read in a file of environment variables
			'-h' help for exec
			'-i': Keep STDIN open even if not attached.
			'--privileged\[=false\]': give extended privileges to the command
			'-t', '--interactive\[=false\]': Allocate a pseudo-TTY to allow interaction with container
			'-u', '--user="" ': Username or UID (format: "\[:\]")
			'-w', '--workdir="" ': working directory inside the container
		examples:
			to open an interactive shell in a running container named 'my_container', you would use:
				docker exec -it my_container bash
	docker builder
		manage builds
	