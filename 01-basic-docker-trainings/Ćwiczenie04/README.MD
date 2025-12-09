# Basic docker trainging

## Ćwiczenie 4: Udostępnianie obrazów

### Pierwsze kroki

> Polecenie: `docker login`

![Screenshot01](scr01.png)

### Tagowanie obrazów

> Polecenie: `docker tag kuba/ping kuba/ping:1.0`

> Polecenie: `docker images`

![Screenshot02](scr02.png)

> Polecenie: `docker rmi kuba/ping`

> Polecenie: `docker images`

![Screenshot03](scr03.png)

### Wysyłanie obrazów (push)

> Polecenie: `docker push masalski22/ping:1.0`

![Screenshot03](scr03.png)

[Dockerhub](https://hub.docker.com/r/masalski22/ping)
