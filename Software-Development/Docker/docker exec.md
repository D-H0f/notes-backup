***description:***
	alias: "docker container exec", "docker-container-exec"
	run a process ina running container.
	The command started using docker exec will only run while the container's primary process (PID 1) is running, and will not be restarted if the container is restarted.
	If the container is paused, then the *docker exec* command will wait until the container is unpaused, and then run.
	
***syntax:***
	docker exec \[FLAGS\] CONTAINER COMMAND \[ARG...\]
	-'FLAGS': optional flags to modify the action of the 'docker exec' command.
	-'CONTAINER': The name or ID of the container where you want to run the command
	-'COMMAND': The command you want to run inside the container.
	-'ARG...': Any arguments for the command you are running.
***flags:***
	'-d', '--detach\[=false\]': Detached mode: run command in the background
	'-e', '--env=': set environment variables.
	'--env-file=': read in a file of environment variables
	'-h' help for exec
	'-i': Keep STDIN open even if not attached.
	'--privileged\[=false\]': give extended privileges to the command
	'-t', '--interactive\[=false\]': Allocate a pseudo-TTY to allow interaction with container
	'-u', '--user="" ': Username or UID (format: "\[:\]")
	'-w', '--workdir="" ': working directory inside the container
***examples:***
	docker exec -it my_container bash
		this command opens an interactive bash terminal in the container 'my_container'.