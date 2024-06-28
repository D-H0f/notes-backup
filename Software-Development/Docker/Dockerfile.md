
Overview:
	- Docker can build images automatically by reading the instructions from a Dockerfile.
	- A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.
Dockerfile Instructions:
	[ADD](Dockerfile%20ADD.md) : Add local or remote files and directories.
	[ARG](Dockerfile%20ARG.md) : Use build-time variables.
	[CMD](Dockerfile%20CMD.md) : Specify default commands.
	[COPY](Dockerfile%COPY.md) : Copy files and directories.
	[ENTRYPOINT](Dockerfile%20ENTRYPOINT.md) : Specify default executable.
	[ENV](Dockerfile%20ENV.md) : Set environment variables.
	[EXPOSE](Dockerfile%20EXPOSE.md) : Describe which ports your application is listening on.
	[FROM](Dockerfile%20FROM.md) : Create a new build stage from a base image.
	[HEALTHCHECK](Dockerfile%20HEALTHCHECK.md) : Check a container's health on startup.
	[LABEL](Dockerfile%20LABEL.md) : Add metadata to an image.
	[MAINTAINER](Dockerfile%20MAINTAINER.md) : Specify the author of an image.
	[ONBUILD](Dockerfile%20ONBUILD.md) : Specify instructions for when the image is used in a build.
	[RUN](Dockerfile%20RUN.md) : Execute build commands.
	[SHELL](Dockerfile%20SHELL.md) : Set the default shell of an image.
	[STOPSIGNAL](Dockerfile%20STOPSIGNAL.md) : Specify the system call signal for exiting a container.
	[USER](Dockerfile%20USER) : Set user and group ID.
	[VOLUME](Dockerfile%20VOLUME) : Create volume mounts.
	[WORKDIR](Dockerfile%20WORKDIR.md) : Change working directory.
Format:
	\#comment
	INSTRUCTION arguments
The instruction is not case sensitive. However, convention is for them to be uppercase to distinguish them from arguments more easily.

File layout:
	Docker runs instructions in a Dockerfile in order. A Dockerfile must begin with a [FROM](Dockerfile%20FROM.md) instruction. This may be after [parser directives](Dockerfile%20parser%20directives.md), comments, and globally scoped [ARGs](Dockerfile%20ARG.md). The FROM instruction specifies the parent image from which you are building. FROM may only be preceded by one or more ARG instructions, which declare arguments that are used in FROM lines in the Dockerfile.
BuildKit treats lines that begin with '#' as a comment, unless the line is a valid [parser directive](Dockerfile%20parser%20directives.md). A '#' marker anywhere else in a line is treated as an argument.