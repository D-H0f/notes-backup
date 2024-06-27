description:
	alias for: *docker-image-pull*, *docker image pull*
	This command pulls down an image or a repository from a registry. If there is more than one image for a repository, then all images for that repository name can be pulled down including any tags.
	If you do not specify a REGISTRY_HOST, the command uses Docker's public registry located at **registry-1.docker.io** by default.
syntax:
	docker pull \[FLAGS\] NAME\[:TAG|@DIGEST\]
		'docker pull'
			the base command
		'\[FLAGS\]'
			optional flags to modify the behaviour of the command
		'NAME'
			the name of the image to be pulled.
		'\[:TAG|@DIGEST\]'
			optional tag or digest. if you dont specify a tag, Docker will pull the 'latest' tag by default.
flags:
	'--all-tags'
		Download all tagged images in the repository
examples:
	docker pull debian
		downloads the debian image from the public Docker registry. Since no TAG is specified, it downloads the default: "debian:latest"