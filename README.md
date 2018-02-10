# Docker-composeによるWeb開発環境ベース

## nginx
mainline-alpineを使用
<https://hub.docker.com/_/nginx/>
<https://github.com/nginxinc/docker-nginx/blob/f8fad321cf58d5cbcafa3d9fa15314b8a77b5e65/mainline/alpine/Dockerfile>
自己証明書にてhttp2のセットアップを行っている

* nginxの設定ファイル web/default.conf
* nginxのログ出力     data/logs/nginx/
* web root  data/html


## php
php7-fpm-alpineを使用
<https://hub.docker.com/_/php/>
<https://github.com/docker-library/php/blob/fd8e15250a0c7667b161c34a25f7916b01f72367/7.2/alpine3.6/fpm/Dockerfile>
Dockerfileにてpdo_mysql mysqli mbstringをインストール

* php.iniの場所　php7/php.ini
* データベースのアクセスアカウントは.envに記載

## mysql
mysql5.7を使用
<https://hub.docker.com/_/mysql/>
<https://github.com/docker-library/mysql/blob/607b2a65aa76adf495730b9f7e6f28f146a9f95f/5.7/Dockerfile>
データベースのアクセスアカウントは.envに記載

* mysqlのログ出力 data/logs/mysql
* mysqlの設定ファイル db/my.cnf
* mysqlの初期化用ファイル db/initial.sql


## データベース接続サンプルについて
db/initial.sqlにサンプルテーブルを初期化するスキーマがある。
data/html/index.phpにアクセスする毎にinsertとselectで値が増えるので接続確認用に使えます。
初期確認が終わったら、initial.sqlを書き換えてサンプルテーブルを破棄してください。

