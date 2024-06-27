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
	[[docker run]]
		starts a docker container with a specified environment image.
	[[docker pull]]
		downloads a docker image.
	docker image
		manage images
		subcommands:
			docker image pull ([[docker pull]])
	[[docker ps]]
		lists running docker containers.
	[[docker exec]]
		executes a command in a docker container.
	[[docker rm]]
		remove one or more containers.
	[[docker build]]
		Build an image from a dockerfile

TAGS: #docker #linux #tools