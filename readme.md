# docker notları

MYSQL

NODEJS

Nodejs imaj oluşturma ( Dockerfile arıyor)

docker build -t engin-backend .

From <https://github.com/nodejs/docker-node/blob/main/README.md#how-to-use-this-image>

Nodejs container oluşturma

docker run -it --rm --name engin-container-backend engin-backend

From <https://github.com/nodejs/docker-node/blob/main/README.md#how-to-use-this-image>
From <https://github.com/nodejs/docker-node/blob/main/README.md#how-to-use-this-image>

docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
docker run --name mysql-engin -e MYSQL_ROOT_PASSWORD=123456 -d mysql
Port belirt
docker run --name mysql-engin -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql

Docker bir modem gibi çalışır.
Dış ipden gelen istekleri iç ipye dağıtır, gönderir bir modem.
Docker ise gelen istekleri ilgili portuna yöneltir 4000:4000 diyince içerisine dağıtır.

//containerlari ayrıntılı şekilde verir.
Docker ps -a

//containeri çalıştır ve bashine gir.
docker exec -it c46e6682fbaa /bin/bash

//containeri run et. 4000 portundan gelen istekleri dockerin içerisindeki 4000 portuna gönder.
docker run -d -p 4000:4000 engin-container-backend

Mysql login
mysql -u root -p

LİNUXTAKİ ve containerlarındaki KOMUTLAR
Nodejs Imageden container oluştur
docker run -it -p 4000:4000 engin-backend /bin/bash

Mysql volume
docker volume create mysql-volume

MysqlDump
mysqldump -root -123456 -localhost USER_DATABASE > test.sql
apt-get update
apt-get -y install curl
MYSQL EXPORT
apt-get install -y mariadb-client

mysqldump -u root-p database_name>test.sql

From <https://www.digitalocean.com/community/tutorials/how-to-import-and-export-databases-in-mysql-or-mariadb>

MYSQL IMPORT
CREATE DATABASE new_database;

mysql -u root -p weekly < test.sql

From <https://www.digitalocean.com/community/tutorials/how-to-import-and-export-databases-in-mysql-or-mariadb>

Container içine dosya kopyalama:
docker cp ./test.sql 8ecdb1aa5cc1:/docker-entrypoint-initdb.d/

Mysql içerisindeki sql dosyasını database de çalıştır.
mysql -u root -p weekly < /docker-entrypoint-initdb.d/test.sql
Bu da localden aynı işlemdi postgre için yapmıştık
docker exec -it 3818472804f5 /bin/bash -c "psql -U postgres -w postgres -f /docker-entrypoint-initdb.d/PostgreSqlDB.sql
