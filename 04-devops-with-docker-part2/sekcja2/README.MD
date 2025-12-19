# Sekcja 2

## Sieci Dockera

### Ćwiczenie 2.4

[docker compose](./cw2.4/docker-compose.yml)

![Screenshot 01](scr01.png)
![Screenshot 02](scr02.png)


### Skalowanie

[Docker compose](docker-compose.whoami.yml)


> Polecenie : `docker-compose -f docker-compose.whoami.yml up --scale whoami=3`

> Polecenie : `docker-compose -f docker-compose.whoami.yml port --index 1 whoami 8000`


> Polecenie : `docker-compose -f docker-compose.whoami.yml port --index 2 whoami 8000`


> Polecenie : `docker-compose -f docker-compose.whoami.yml port --index 3 whoami 8000`

![Screenshot 03](scr03.png)
![Screenshot 04](scr04.png)

![Screenshot 05](scr05.png)

> Polecenie : `curl localhost:80`

![Screenshot 06](scr06.png)


> Polecenie : `curl whoami.colasloth.com`

![Screenshot 07](scr07.png)


![Screenshot 08](scr08.png)

Zmiania działa bez restartu kontenera

![Screenshot 09](scr09.png)

### Ćwiczenie 2.5
> Polecenie : `docker-compose up --scale compute=3`

![Screenshot 10](scr10.png)