Description:
	- The WORKDIR instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the [[Dockerfile]].
	- If the WORKDIR doesn't exist, it will be created even if it's not used in any subsequent Dockerfile instruction.
	- The WORKDIR instruction can be used multiple times in a Dockerfile. If a relative path is provided, it will be relative to the path of the previous WORKDIR instruction. For example:
		```WORKDIR /a
		WORKDIR b
		WORKDIR c
		RUN pwd```
		The output of the final pwd command would be /a/b/c
Syntax:
	`WORKDIR /path/to/working/directory`