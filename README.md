# フロントエンド開発

## Overview

- この PJ は`Docker`及び`docker-compose`がインストールされていることが前提です。
- フロントエンドのフレームワークは`React`を採用しています。
- プロジェクトディレクトリは`frontend`です。
- 環境構築については`create-react-app`を使用しています。
- `yarn or npm`コマンドで`node_module`をインストールします。

## docker-compose.yaml

```yaml
# docker-composeのバージョン
version: '3.7'
services:
  # サービス名
  node:
    # イメージは提供済みのイメージを使用
    image: belldata/node-react:yarn # belldata/node-react:npm
    # ttyをtrueにすることでコンテナがすぐに終了してしまうのを防ぐ
    tty: true
    # コンテナ名称(任意)
    container_name: example
    # 階層を指定(その配下にfrontendが作成され、そこがプロジェクトディレクトリとなる)
    volumes:
      - ./:/app
    # 任意のポート番号
    ports:
      - '19999:19999'
```

## 立ち上げ

`docker-compose up -d`

## イメージへログイン

`docker exec -it コンテナ名 bash`

## イメージへのログイン後はフロントエンド開発(割愛)

```bash
npx create-react-app my-app --template typescript
or
yarn create react-app my-app --template typescript
```

## 早見表

| npm (v5)                                   | Yarn                               |
| :----------------------------------------- | :--------------------------------- |
| npm install                                | yarn install                       |
| None                                       | yarn install --flat                |
| None                                       | yarn install --har                 |
| npm install --no-package-lock              | yarn install --no-lockfile         |
| None                                       | yarn install --pure-lockfile       |
| npm install [package name]                 | yarn add [package name]            |
| npm install [package name] --save-dev      | yarn add [package name] --dev      |
| None                                       | yarn add [package name] --peer     |
| npm install [package name] --save-optional | yarn add [package name] --optional |
| npm install [package name] --save-exact    | yarn add [package name] --exact    |
| None                                       | yarn add [package name] --tilde    |
| npm install [package name] --global        | yarn global add [package name]     |
| npm update --global                        | yarn global upgrade                |
| npm rebuild                                | yarn install --force               |
| npm uninstall [package name]               | yarn remove [package name]         |
| npm cache clean                            | yarn cache clean [package name]    |
| rm -rf node_modules && npm install         | yarn upgrade                       |

- [React](https://ja.reactjs.org/)
- [create-react-app](https://create-react-app.dev/)
