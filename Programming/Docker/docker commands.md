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
	docker run \[options\] \[image\]
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
			
	docker builder
		manage builds
	