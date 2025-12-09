# Basic docker trainging

## Ćwiczenie 1: Uruchamianie kontenerów

### Pobieranie obrazu


> Polecenie: `docker images`

![Screenshoot 01](scr01.png)

> Polecenie: `docker search ubuntu`

![Screenshoot 02](scr02.png)

> Polecenie: `docker pull ubuntu:22.04`

![Screenshoot 03](scr03.png)

> Polecenie: `docker images`

![Screenshoot 04](scr04.png)


> Polecenie: `docker rmi 104ae83764a5`

![Screenshoot 05](scr05.png)

> Polecenie: `docker images`

![Screenshoot 06](scr06.png)


--- 

### Uruchamainie kontenerów

> Polecenie: `docker run -it --name ubuntu-shell ubuntu:22.04 /bin/bash`

![Screenshoot 07](scr07.png)


```bash
ls pwd exit
```

![Screenshoot 08](scr08.png)


> Polecenie: `docker ps -a`

![Screenshoot 09](scr09.png)

> Polecenie: `docker start -i ubuntu-shell`

![Screenshoot 10](scr10.png)

> Polecenie: `docker stop ubuntu-shell`

> Polecenie: `docker rm ubuntu-shell`

> Polecenie: `docker ps -a`


![Screenshoot 11](scr11.png)
