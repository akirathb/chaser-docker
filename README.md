
# chaser-docker

## About

   U16 Kushiro プログラミングコンテストの 競技部門の CHaser サーバの実装の一つ、lrks さんの https://github.com/lrks/chaserver を 超簡単にインストールする。

## 動いた環境

+   ubuntu16.04LTS 

+   RaspberryPi2  http://blog.hypriot.com/ Version 0.8.0 Barbossa


## Install

## 準備

+ docker 及び docker-compose をインストールする

### Ubuntu

    git clone https://github.com/akirathb/chaser-docker.git
    cd chaser-docker
    docker-compose built

### Raspberry Pi2

    Docker がインストールされている ラズバイのイメージをダウンロードする http://blog.hypriot.com/downloads/
    2016/6/26 現在最新は Version 0.8.0 Barbossa https://downloads.hypriot.com/hypriotos-rpi-v0.8.0.img.zip
   
    SDカードにイメージを書き込む (ラズビアンとかと同様）
    ブートする Version 0.8.0 では ユーザ/パスワードは pirate/hypriot
    
    このユーザで docker が使える
    取得するDocker イメージを ラズバイ用に Dockerファイルの修正

    manager/Dockerfile
    server/Dockerfile

    共に

    FROM node  を
    FROM hypriot/rpi-node に修正

    Step 1 : FROM hypriot/rpi-node
    Get https://registry-1.docker.io/v2/hypriot/rpi-node/manifests/latest: Get https://auth.docker.io/token?scope=repository%3Ahypriot%2Frpi-node%3Apull&service=registry.docker.io: dial tcp: lookup auth.docker.io: no such host

    と怒られた時 https://linuxconfig.org/docker-dial-tcp-lookup-index-docker-io-no-such-host-fix に Soluion が

    host auth.docker.io  で、IPアドレスを検索　複数表示されるので、1つを選んで auth.docker.io を /etc/hosts に書く

    あとは ubuntu と同じ

    
## Start Server 

    docker-compose up -d

## Use Server

    http://yourserver:3000/　にブラウザからアクセス

## Stop Server

    docker-compose down 


