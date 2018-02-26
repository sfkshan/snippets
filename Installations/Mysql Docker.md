# Installing MySQL in docker

## Pulling image

```docker pull mysql/mysql-server:tag```

## To list the images in docker

```docker images```

## To start a new instance

```docker run --name=mysql1 -d mysql/mysql-server:tag```

## For the first time run this command to get the random generated root password

```docker logs mysql1 2>&1 | grep GENERATED```

## Connecting to the instance of the MySQL running in the docker container

```docker exec -it mysql1 mysql -uroot -p```

## To change the root password

```ALTER USER 'root'@'localhost' IDENTIFIED BY 'newpassword';```

## Stop/Restart and deleting the container

```docker stop mysql1
docker restart mysql1
docker rm mysql1
docker rm mysql1 -v```

-v option to delete the data directory