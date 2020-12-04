<div style="display: flex; justify-content: center">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAMTxDNTb9Uf0QUaMIp4yOTJlXzyFzAyO7tw&usqp=CAU" />

</div>

#Trello Clone

## Create network

```
docker network create trello-clone
```


## Copy .env.example
```
cp .env.example .env
```
## Edit DATA_PATH_HOST in env File (Backup dữ liệu mysql để không bị mất khi tắt container lưu tại máy mình)

## Build Docker
```
docker-compose up -d --build
```
## Composer update
```
docker-compose exec php-fpm composer update
```
## Change permission Storage and Vendor
```
docker-compose exec php-fpm chmod -R 777 storage/ vendor/
```

## Run localhost tại cổng 8000
http://localhost:8000


## run testing
```
docker-compose exec php-fpm ./vendor/bin/phpunit
```

