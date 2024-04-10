# Docker Getting Started Tutorial

dockerのチュートリアルを写経して、dockerの基礎について勉強する

https://docs.docker.jp/get-started/02_our_app.html

## execution command

#### 実行
> docker run -dp 127.0.0.1:3000:3000 getting-started

#### lsコマンド
> docker ps

#### docker アカウントへのログイン
> docker login -u username  
> Password:

#### タグの作成
> docker tag getting-started username/getting-started

e.g.(repositoryの作成)  
> docker tag tag-test username/hogetest

#### イメージの送信
> docker push username/getting-started

e.g.  
> docker push username/hogetest

#### ローカル上のイメージ確認
> docker image ls

> docker run -dp 127.0.0.1:3000:3000 images

## データベースの保持

https://docs.docker.jp/get-started/05_persisting_data.html

コマンドラインからコンテナへのアクセス
> docker exec <container-id> cat /data.txt

コンテナを起動して、ボリュームのマウントを指定する
> docker run -dp 127.0.0.1:3000:3000 --mount type=volume,src=todo-db,target=/etc/todos <image-name>


> docker volume inspect todo-db
```
[
    {
        "CreatedAt": "2024-04-10T13:47:31Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/todo-db/_data",
        "Name": "todo-db",
        "Options": null,
        "Scope": "local"
    }
]
```

## Bind Mount
バインドマウントのコマンド
> docker run -it --mount "type=bind,src=$pwd,target=/src" ubuntu bash

開発用のコンテナでアプリを実行(/app へ移動必要)
> docker run -dp 127.0.0.1:3000:3000 -w /app --mount "type=bind,src=$pwd,target=/app" node:18-alpine sh -c "yarn install && yarn run dev"

ログの出力
> docker logs <container-id>

ソースコードを修正することですぐにアプリに反映される。

## 複数コンテナのアプリ