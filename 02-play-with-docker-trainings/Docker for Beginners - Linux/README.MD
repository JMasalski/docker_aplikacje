# Task 0: Prerequisites

> Polecenie: `git clone https://github.com/dockersamples/linux_tweet_app`

![scr01](scr01.png)

# Task 1: Run some simple Docker containers

### Run a single task in an Alpine Linux containe

> Polecenie: `docker container run alpine hostname`

![scr02](scr02.png)

> Polecenie: `docker container ls --all`

![scr03](scr03.png)

### Run an interactive Ubuntu container

> Polecenie: `docker container run --interactive --tty --rm ubuntu bash`

![scr04](scr04.png)

Polecenie:
```
ls /
ps aux
cat /etc/issue
```

![scr05](scr05.png)

Polecenie:
```
exit
cat /etc/issue
```
![scr06](scr06.png)

### Run a background MySQL container

Polecenie 
``` 
docker container run \
--detach \
--name mydb \
-e MYSQL_ROOT_PASSWORD=my-secret-pw \
mysql:latest

docker container ls
```

![scr07](scr07.png)

> Polecenie: `docker container logs mydb`

![scr08](scr08.png)

> Polecenie: `docker container top mydb`

![scr09](scr09.png)

> Polecenie: `docker exec -it mydb \
 mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version`

Polecenie:
```
docker exec -it mydb sh
mysql --user=root --password=$MYSQL_ROOT_PASSWORD --version
exit
```
![scr10](scr10.png)

# Task 2: Package and run a custom app using Docker

### Build a simple website image

> Polecenie: `cd ~/linux_tweet_app cat Dockerfile`

![scr11](scr11.png)


Polecenie: 
```
export DOCKERID=masalski22
docker image build --tag $DOCKERID/linux_tweet_app:1.0 .
```

![scr12](scr12.png)



Polecenie: 
``` 
docker container run \
--detach \
--publish 80:80 \
--name linux_tweet_app \
$DOCKERID/linux_tweet_app:1.0
```
![scr13](scr13.png)
![scr14](scr14.png)

# Task 3: Modify a running website

### Start our web app with a bind mount

Polecenie: 
``` 
docker container run \
--detach \
--publish 80:80 \
--name linux_tweet_app \
--mount type=bind,source="$(pwd)",target=/usr/share/nginx/html \
$DOCKERID/linux_tweet_app:1.0
```

![scr15](scr15.png)
![scr16](scr16.png)

### Modify the running website

Polecenie
```
docker container run \
--detach \
--publish 80:80 \
--name linux_tweet_app \
--mount type=bind,source="$(pwd)",target=/usr/share/nginx/html \
$DOCKERID/linux_tweet_app:1.0

cp index-new.html index.html
```

![scr17](scr17.png)

W vi edytowałem jeszcze samemu plik index.html

![scr18](scr18.png)

Polecenie
```
docker rm --force linux_tweet_app

docker container run \
--detach \
--publish 80:80 \
--name linux_tweet_app \
$DOCKERID/linux_tweet_app:1.0
```

![scr19](scr19.png)
![scr20](scr20.png)

### Update the image

Polecenie
```
docker image build --tag $DOCKERID/linux_tweet_app:2.0 .

docker image ls
```

![scr21](scr21.png)


### Test the new version

Polecenie
```
docker container run \
--detach \
--publish 80:80 \
--name linux_tweet_app \
$DOCKERID/linux_tweet_app:2.0

docker container run \
--detach \
--publish 8080:80 \
--name old_linux_tweet_app \
$DOCKERID/linux_tweet_app:1.0
```

![scr22](scr22.png)
![scr23](scr23.png)

### Push your images to Docker Hub

Polecenie
```
docker image ls -f reference="$DOCKERID/*"

docker login
```

![scr24](scr24.png)

Polecenie
```
docker image push $DOCKERID/linux_tweet_app:1.0

docker image push $DOCKERID/linux_tweet_app:2.0
```

![scr25](scr25.png)

![scr26](scr26.png)

[Dockerhub](https://hub.docker.com/r/masalski22/linux_tweet_app)