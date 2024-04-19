# Docker Getting Started Tutorial

https://github.com/dockersamples/buildme

## execution command

#### イメージの構築
> docker build --tag=buildme .

~~※ bin/clientとbin/serverディレクトリは空で作っておく~~

go.sumも作っておく必要あり

#### コンテナの実行
構築したイメージには2つのバイナリが入っていて、１つはサーバ、もう１つはクライアントになる。

コンテナをイメージからでタッチモードで呼び出す
> docker run --name=buildme --rm --detach buildme

ENTRYPOINTをbin/serverにしているので、デタッチモードではserver.main.goが呼び出される。

buildmeコンテナでクライアントバイナリを呼び出すコマンド
> docker exec -it buildme /bin/client

####
https://docs.docker.jp/build/guide/layers.html