# Docker image collection

https://hub.docker.com/
https://docs.docker.com/get-started/part2/

## Build image

```
sudo docker build -t majkel89/php:7.2 .
```

## Run image

```
sudo docker run majkel89/php:7.2
```

## Push image

```
sudo docker login
sudo docker tag image majkel89/php:7.2
sudo docker push majkel89/php:7.2
```
