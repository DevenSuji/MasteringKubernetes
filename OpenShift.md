sudo podman search rhel

sudo podman pull rhell

sudo podman images

sudo podman run rhel7:7.5 

sudo podman run rhel7:7.5 echo "Hello World"

-d option runs the process in the background

--name Allows you to specify unique name for a container. If not provided, a name is automatically generated.

-t Creats a pseudo terminal

-i Keeps STDIN open even if not attached.

sudo podman run -it rhel7:7.5 /bin/bash

-e : Environment variables

-p : Port forward (10080:80)

sudo podman run --name mysql-custom \ -e MYSQL_USER=redhat -e MYSQL_PASSWORD=r3dh4t \ -d mysql:5.5

# Sample Docker File
*********************************************

# This is a Comment line.

FROM rhel7.3
LABEL description="This is a custom httpd container image"
MAINTAINER Deven Suji <DevenSuji@outlook.com>
RUN yum install -y httpd
EXPOSE 443
ENV LogLevel "info"
ADD http://someserver.com/filename.pdf /var/www/html
COPY /src/ /var/www/html
USER apache
ENTRYPOINT ["/usr/sbin/httpd"]
CMD ["-D","FOREGROUND"]

*********************************************
# Command to build a container 

podman build -t NAME:TAG DIR

Where:
NAME: Name that you want to give to the docker file.
TAG: A Tag that you want to give to the Docker File.
DIR: The path of the directory where the docker file is saved.



