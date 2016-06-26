# chaser-docker

## About

   https://github.com/lrks/chaserver を 簡単にインストールする

## 動いた環境

+   ubuntu16.04LTS　node 

+   RaspberryPi2  http://blog.hypriot.com/ Version 0.8.0 Barbossa


## Install

    cd chaser
    docker build -t chaser/u16 .
    cd ..
    cd cserve
    docker build -t server/u16 .
    cd ..

    docker images

## Start 

    docker-compose up -d


## Use

    http://yourserver:3000/

## Stop

    docker-compose down 



