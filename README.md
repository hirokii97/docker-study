# docker-study

## イメージの作成 
docker image build -t sample/webrick:latest .
docker image build -t [イメージの名前] [ディレクトリ]
docker image ls

## コンテナの起動
docker container run -p 8000:8000 --name webrick sample/webrick:latest
docker container run -p [ポート番号] --name [コンテナ名] [イメージ名]
docker container ls

##　Dcokerのマウント機能を使って、ディレクトリをコンテナと同期する
-v "$(pwd)"/src:/var/www/htmlを追加
docker container run -p 8000:8000　-v "$(pwd)"/src:/var/www/html --name webrick sample/webrick:latest

## コンテナのログ出力
docker container logs webrick

## コンテナ停止
docker container stop webrick

## コンテナ再起動
docker container start webrick
docker container ls -a

## コンテナ削除
docker container rm webrick

## コンテナ内のコマンド実行
docker container exec webrick ruby -v
