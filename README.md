# Docker_for_Rails_BestPractice
DockerでRails5+Mysql+Nginx+pumaの環境を作る

## プロジェクトフォルダの生成

```
$ mkdir Rails_APP
$ cd Rails_APP
```

## 環境をクローン

```
$ git clone https://github.com/tunagohan/Docker_for_Rails_BestPractice.git
$ cd Docker_for_Rails_BestPractice
```

## アプリケーションのクローン

```
$ git clone {動かしたいRails_APP}
```

## 最終的なディレクトリ構成図

```
Rails_APP
  └── Docker_for_Rails_BestPractice
         │
         ├── {動かしたいRails_APP}
         │    └── Railsアプリを配置
         ├─ mysql
         │    └── Dockerfileやconfig
         ├─ nginx
         │    └── Dockerfileやconfig
         ├─ rails
         │    └── Dockerfileやconfig
         │
         ├── docker-compose.yml
         └── .env
```

## 始め方

`Docker_for_Rails_BestPractice` 上で以下のコマンドを叩く

### up

```
$ docker-compose up -d
```

### db create

```
$ docker-compose run --rm app rake db:create
```

### db migrate

```
$ docker-compose run --rm app rake db:migrate
```
