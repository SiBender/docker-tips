# docker-tips

Удалить все контейнеры
docker rmi $(docker images -q)


Переменная окружения
docker run -e MYSQL_ROOT_PASSWORD=docker -d mysql

-d запуск в режиме daemon


Логи контейнера
	docker logs <>


docker run -d --name my-ubuntu ubuntu


bash внутри контейнера
docker exec -it <condainerId или имя> bash


Установить переменную окружения


Проброс порта  -p
 docker run -d -p 8888:80 --name dim-apache httpd

Проверить правила переназначенных портов
sudo iptables -L DOCKER -t nat

docker port <>
docker inspect <>

docker start <>
docker stop  <>
docker kill  <>


Подключение каталога (постоянное хранилище)
-v /host/path:/path/in/comtainer
docker run -dit --name my-apache-app -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4


Тэг для публикации в registry
docker tag образ[:тег] [сервер][имя пользователя]имя[:тег]



Экспорт
docker export
	docker export -o <file-name>.tar <container-name>
docker import (из tar архива в хранилище образов)
	docker import <file-name>.tar <image-name>:1.0 (или какой там тег...)
	
docker save
	docker save -o saved-mysql.tar mysql
docker load
	docker load -i saved-mysql.tar















