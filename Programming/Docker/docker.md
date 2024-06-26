A replacement for running software in virtual machines
where a VM virtualizes hardware, docker virtualizes an OS environment

docker runs processes on containers, quarantined environments that can be as lightweight or as powerful as needed, and can be thought of as micro computers.

to get a specific environment, you can create an image of your current environment, or you can use a specific one offered by docker by using:
	docker pull ubuntu
	or
	docker pull python
and add
	FROM python:3.12-bookworm
to your Dockerfile to use it as the container environment

here is a list of docker commands: [[docker commands]]

TAGS: #docker #programming #linux 