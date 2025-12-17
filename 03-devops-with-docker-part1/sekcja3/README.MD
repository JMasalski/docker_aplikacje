# Sekcja 3

### Skąd biorą się obrazy?

> Polecenie : `docker search hello-world`

![Screenshot 01](scr01.png)

### Szczegółowe spojrzenie na obraz

> Polecenie : `docker pull ubuntu`

![Screenshot 02](scr02.png)

> Polecenie : `docker pull ubuntu:22.04`

![Screenshot 03](scr03.png)

> Polecenie : `docker tag ubuntu:22.04 fav_distro:jammy_jellyfish `

![Screenshot 04](scr04.png)

### Ćwiczenie 1.5

> Polecenie : `docker pull devopsdockeruh/simple-web-service:alpine `

![Screenshot 05](scr05.png)

> Polecenie : `docker run -it devopsdockeruh/simple-web-service:alpine`

![Screenshot 06](scr06.png)

> Polecenie : `docker ps`

> Polecenie : `docker exec -it awesome_chebyshev sh`

> Polecenie : `tail -f ./text.log`

![Screenshot 07](scr07.png)

### Ćwiczenie 1.6

> Polecenie : `docker run -it devopsdockeruh/pull_exercise`

![Screenshot 08](scr08.png)

> Polecenie : `docker exec -it happy_joliot sh`

> Polecenie : `ls`

> Polecenie : `cat index.js`

![Screenshot 10](scr10.png)
![Screenshot 11](scr11.png)

> Polecenie : `basics`

![Screenshot 09](scr09.png)

### Budowanie obrazów

- [Skrypt](./hello.sh)

![Screenshot 12](scr12.png)

- [Dockerfile](./Dockerfile.budowanie)

> Polecenie: `docker build . -t hello-docker`
![Screenshot 13](scr13.png)


> Polecenie: `docker image ls`

![Screenshot 14](scr14.png)

> Polecenie: `docker run hello-docker`

![Screenshot 15](scr15.png)

> Polecenie: `docker run -it hello-docker sh`
![Screenshot 16](scr16.png)

> Polecenie: `docker ps`

> Polecenie: `touch additional.txt`

> Polecenie : `docker cp ./additional.txt silly_pare:/usr/src/app/`

![Screenshot 16](scr16.png)

> Polecenie : `ls`


![Screenshot 17](scr17.png)

> Polecenie :  `docker diff silly_pare`

![Screenshot 18](scr18.png)

> Polecenie :  `docker commit silly_pare hello-docker-additional`

> Polecenie :  `docker image ls`

![Screenshot 19](scr19.png)


> Polecenie :  `docker build . -t hello-docker:v2`

![Screenshot 20](scr20.png)

> Polecenie :  `docker run hello-docker-additional ls`

> Polecenie :  `docker run hello-docker:v2 ls` 

![Screenshot 21](scr21.png)

### Ćwiczenie 1.7

[Dockerfile](Dockerfile.cw)

[Skrypt](script.sh)

> Polecenie :  `docker build -f ./Dockerfile.cw -t curler .` 

![Screenshot 22](scr22.png)

> Polecenie :  `docker run -it curler` 

![Screenshot 23](scr23.png)

### Ćwiczenie 1.8

[Dockerfile](Dockerfile.cw2)

> Polecenie :  `docker build -f ./Dockerfile.cw2 -t web-server .`

> Polecenie : `docker run web-server`

![Screenshot 24](scr24.png)
