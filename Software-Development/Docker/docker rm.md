***description***:
	alias: "docker container rm", "docker-container-rm"
	*docker rm* will remove one or more containers from the host node. The container name or ID can be used. This does not remove images. You cannot remove a running container unless you use the -f option.
***syntax***:
	docker rm \[FLAGS\] CONTAINER \[CONTAINER...\]
		docker rm:
			The base command
		\[FLAGS\]:
			Optional flags to modify the behavior of the command
		CONTAINER:
			The container to be removed.
		\[CONTAINER...\]
			Any additional containers to be removed, seperated by spaces.
***flags***:
	-f:
		Force the removal of a running container (uses SIGKILL)
	-l:
		Remove the specified link.
		This does not remove the container itself, but rather the link that connects containers. It is generally used in situations where containers are linked together.
	-v:
		Removes anonymous volumes associated with the container.
***examples***:
	docker rm mycontainer
		This removes an inactive container with the name 'mycontainer'
	docker rm 185be57433e4
		This removes an inactive container with the ID: "185be57433e4"
	docker rm -f mycontainer mycontainer2
		This removes two running containers, 'mycontainer', and 'mycontainer2'