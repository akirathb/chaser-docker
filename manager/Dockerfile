FROM node

## RaspberryPi
# FROM  hypriot/rpi-node

#ENV http_proxy 
#ENV https_proxy 
#ENV no_proxy 

RUN apt-get -y update
RUN apt-get -y install unzip
RUN apt-get -y install python-pip

#RUN npm -g config set proxy 
#RUN npm -g config set https-proxy 


RUN wget https://github.com/lrks/chaserver/archive/master.zip
RUN unzip master.zip

WORKDIR /chaserver-master

RUN npm -y install socket.io

CMD node ./manager/manager.js

EXPOSE 3000

