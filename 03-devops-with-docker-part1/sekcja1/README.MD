# Sekcja 1

### Uruchamianie kontenerów


> Polecenie: `docker container run hello-world`

![Screenshoot 01](scr01.png)

### Obrazy (images)

> Polecenie: `docker container run -it ubuntu sh -c 'apt update && apt install -y curl && curl https://www.google.com'`

![Screenshoot 02](scr02.png)
![Screenshoot 03](scr03.png)

### Zarządzanie kontenerami

> Polecenie: `docker container ls -a`

> Polecenie: `docker container ls`

![Screenshoot 04](scr04.png)

> Polecenie: `docker container stop 3cfc0e294789`

> Polecenie: `docker container rm 3cfc0e294789`

![Screenshoot 05](scr05.png)

> Polecenie : `docker image pull ubuntu`

![Screenshoot 06](scr06.png)


> Polecenie : `docker image ls`

![Screenshoot 07](scr07.png)

> Polecenie : `docker image rm c35e29c94501`

![Screenshoot 08](scr08.png)
