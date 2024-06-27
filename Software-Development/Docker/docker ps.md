***description***:
	alias for 'docker container ls', 'docker-container-ls'
	List the containers in the local repository. By default this shows only the running containers.
***syntax***:
	docker ps \[FLAGS\]
		docker ps
			The base command
		\[FLAGS\]
			Optional flags to modify the behavior of the command.
***flags***:
	-a
		Show all containers (default shows just running)
	-f, --filter=
		Filter output based on conditions provided
		filters:
			ancestor=(\[:tag\]||image@digest ⟨mailto:image@digest⟩)
				containers created from an image or a descendant.
			before=(|)
			expose=([/]|/[])
			exited= an exit code of
			health=(starting|healthy|unhealthy|none)
			id= a container's ID
			isolation=(default|process|hyperv) (Windows daemon only)
			is-task=(true|false)
			label= or label==
			name= a container's name
			network=(|)
			publish=([/]|/[])
			since=(|)
			status=(created|restarting|removing|running|paused|exited)
			volume=(|)
	--format=""
		Format output using a custom Go template: refer to [link](https://docs.docker.com/go/formatting/) for more information about formatting output with templates
		Valid placeholders for the Go template are listed below:
			.ID
				Container ID
			.Image
				Image ID
			.Command
				Quoted command
			.CreatedAt
				Time when the container was created
			.RunningFor
				Elapsed time since the container was started
			.Ports
				Exposed ports
			.Status
				Container status
			.Size
				Container disk size
			.Names
				Container names
			.Labels
				All labels assigned to the container
			.Label
				Value of a specific label for this container
				example: '{{.Label "com.docker.swarm.cpu"}}'
			.Mounts
				Names of the volumes mounted in this container
			.Networks
				Names of the networks attached to this container
	-n, --last=
		Show n last created containers
	-l, --latest
		Show the latest created container (includes all states)
	-q, --quiet
		Only display container IDs
	-s, --size
		Display total file sizes
***examples***:
	docker ps -a
		Display all containers, including non-running.
	docker ps -aq
		Display only IDs off all containers, including non-running
	docker ps -aq --filter=name=mycontainer
		Display only IDs off all containers that have the name mycontainer