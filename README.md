# docker-cheatsheet

Docker Cheat sheet: 

stop all: 
```
docker kill $(docker ps -q)
```

To clear ALL containers:
```
docker rm -f $(docker ps -a -q)
```

To clear ALL images:
```
docker rmi -f $(docker images -a -q)
```

To clear ALL volumes:
```
docker volume rm $(docker volume ls -q)
```

To clear ALL networks:
```
docker network rm $(docker network ls | tail -n+2 | awk '{if($2 !~ /bridge|none|host/){ print $1 }}')
```
