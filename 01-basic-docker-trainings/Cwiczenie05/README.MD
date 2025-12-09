# Basic docker trainging

## Ćwiczenie 5: Wolumeny

### Uruchamianie serwera

> Polecenie: `docker run --rm -d --name apache -p 80:80 httpd:2.4`

![Screenshot01](scr01.png)


```bash
curl localhost
```
![Screenshot02](scr02.png)


> Polecenie: `docker cp .\01-basic-docker-trainings\Cwiczenie05\index.html apache:/usr/local/apache2/htdocs/`

![Screenshot03](scr03.png)

> Polecenie: `docker stop apache`

> Polecenie: `docker run --rm -d --name apache -p 80:80 httpd:2.4`

> Polecenie: `curl localhost`

![Screenshot04](scr04.png)

### Zarządzanie wolumenami

> Polecenie: `docker volume ls`

![Screenshot05](scr05.png)

> Polecenie: `docker volume create 25083volume`

![Screenshot06](scr06.png)

> Polecenie: `docker volume rm 25083volume`

> Polecenie: `docker volume ls`

![Screenshot07](scr07.png)


## Montowanie wolumenów w kontenerach

> Polecenie: `docker volume create httpd_htdocs`

![Screenshot08](scr08.png)

> Polecenie: `docker run --rm -d --name apache -p 80:80 -v httpd_htdocs:/usr/local/apache2/htdocs/ httpd:2.4`

![Screenshot09](scr09.png)

> Polecenie: `docker cp .\01-basic-docker-trainings\Cwiczenie05\index.html apache:/usr/local/apache2/htdocs/`

> Polecenie: `curl localhost`

![Screenshot10](scr10.png)

> Polecenie: `docker stop apache`

![Screenshot11](scr11.png)

> Polecenie: `docker run --rm -d --name apache -p 80:80 -v httpd_htdocs:/usr/local/apache2/htdocs/ httpd:2.4`

```bash
curl localhost
```


![Screenshot12](scr12.png)

## Montowanie katalogów hosta w kontenerach

> Polecenie: `docker run --rm -d --name apache -p 80:80 -v C:\Users\Kuba\Desktop\docker_aplikacje\01-basic-docker-trainings\Cwiczenie05:/usr/local/apache2/htdocs/ httpd:2.4`


![Screenshot13](scr13.png)

*Przed zmianą*

![Screenshot14](scr14.png)

*Po zmianie*