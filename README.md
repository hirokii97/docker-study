# docker-study

## イメージの作成 
docker image build -t sample/webrick:latest .
docker image ls

## コンテナの起動
docker container run -p 8000:8000 --name webrick sample/webrick:latest
docker container ls


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
