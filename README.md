# Docker Getting Started Tutorial

dockerのチュートリアルを写経して、dockerの基礎について勉強する

https://docs.docker.jp/get-started/02_our_app.html

## execution command

#### 実行
> docker run -dp 127.0.0.1:3000:3000 getting-started

#### lsコマンド
> docker ps

##

This tutorial was written with the intent of helping folks get up and running
with containers and is designed to work with Docker Desktop. While not going too much 
into depth, it covers the following topics:

- Running your first container
- Building containers
- Learning what containers are
- Running and removing containers
- Using volumes to persist data
- Using bind mounts to support development
- Using container networking to support multi-container applications
- Using Docker Compose to simplify the definition and sharing of applications
- Using image layer caching to speed up builds and reduce push/pull size
- Using multi-stage builds to separate build-time and runtime dependencies

## Getting Started

If you wish to run the tutorial, you can use the following command after installing Docker Desktop:

```bash
docker run -d -p 80:80 docker/getting-started
```

Once it has started, you can open your browser to [http://localhost](http://localhost).

