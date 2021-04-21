FROM ubuntu:20.04
RUN ln -snf /usr/share/zoneinfo/Europe/Moscow /etc/localtime
RUN apt update

RUN apt install default-jdk maven docker.io git -y
RUN apt update
RUN mkdir /home/${user}/.jenkins 

VOLUME /home/${user}/.jenkins
WORKDIR /home/${user}

