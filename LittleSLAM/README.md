# 使い方

## macbook側の設定
1. XQuartzをインストール (https://www.xquartz.org/)
2. macbookの再起動
3. XQuartzのメニュー→「環境設定」→「セキュリティ」タブ→「ネットワーク・クライアントからの接続を許可」にチェック
4. XQuartzの再起動
5. コンテナからxの接続を許可 (`xhost + 127.0.0.1`)

## docker
1. Dockerfileのビルド `docker build -t little_slam .`
2. dockerコンテナのビルド
```
docker run -it -e DISPLAY=docker.for.mac.localhost:0 --name little_slam little_slam /bin/bash
```

デモは以下の方法で動かせます.
```
cd LittleSLAM/build/cui
./LittleSLAM ../../dataset/corridor.lsc
```
GUIの画面が出てSLAMで地図を作る様子が確認できれば成功.

# 参考記事
[Docker + macでLittleSLAMを動かす](https://qiita.com/tuttieee/items/488e09e667d2b4391225)
