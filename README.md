#Docker-composeによるWeb開発環境ベース

##nginx
mainline-alpineを使用
自己証明書にてhttp2のセットアップを行っている

* nginxの設定ファイル web/default.conf
* nginxのログ出力     data/logs/nginx/
* web root  data/html


##php
php7-fpm-alpineを使用
Dockerfileにてpdo_mysql mysqli mbstringをインストール

* php.iniの場所　php7/php.ini
* データベースのアクセスアカウントは.envに記載

##mysql
mysql5.7を使用
データベースのアクセスアカウントは.envに記載

* mysqlのログ出力 data/logs/mysql
* mysqlの設定ファイル db/my.cnf
* mysqlの初期化用ファイル db/initial.sql


##データベース接続サンプルについて
db/initial.sqlにサンプルテーブルを初期化するスキーマがある。
data/html/index.phpにアクセスする毎にinsertとselectで値が増えるので接続確認用に使えます。
初期確認が終わったら、initial.sqlを書き換えてサンプルテーブルを破棄してください。



