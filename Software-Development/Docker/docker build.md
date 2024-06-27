***description***:
	The *docker build* command is used to build an image from a [[Dockerfile]]. This command reads the instructions in the Dockerfile and creates a Docker image based on those instructions.
***syntax***:
	docker build \[FLAGS\] PATH/URL/-
		docker build:
			The base command to build an image.
		\[FLAGS\]:
			optional flags to modify the behavior of the command.
		PATH/URL/-
			The location of the build context or Dockerfile. This can be a local file path, a URL, or '-' to read from standard input.
***flags***:
	-t, --tag ""
		Repository names (and optionally tags) to be applied to the resulting image in case of success. 
	-f, --file PATH/Dockerfile
		- Path to the Dockerfile to use. If the path is a relative path and you are building from a local directory, then the path must be relative to that directory.
		- If you are building from a remote URL pointing to either a tarball or a Git repository, then the path must be relative to the root of the remote context. In all cases, the file must be within the build context.
		- The default is [[Dockerfile]].
	--add-host *host*:*ip*
		- Add a custom host-to-IP mapping (host=ip, or host:ip)
		- example: "--add-host myhost:127.0.0.1".
		- This will add the line "127.0.0.1 myhost" to the "/etc/hosts" file in the resulting Docker image.
	--label label=""
		- Adds metadata to the image being built.
		- example:
			docker build --label version="1.0" --label maintainer="me\@mysite\.com" -t myimage:latest
	--rm \[**true**/false\]
		-Remove intermediate containers after a successful build. The default is true.
	--force-rm \[true/**false**\]
		-Always remove intermediate containers, even after unsuccessful builds. The default is false.

TAGS: #docker #linux #tools #commands #docker-build