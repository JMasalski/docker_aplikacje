# Seckja 2

### Uruchamianie i zatrzymywanie kontenerów

> Polecenie: `docker run ubuntu`

![Screenshoot 01](scr01.png)

> Polecenie: `docker run -t ubuntu`

![Screenshoot 02](scr02.png)

> Polecenie: `docker run -it ubuntu`

![Screenshoot 03](scr03.png)

> Polecenie : `docker run -d -it --name looper ubuntu sh -c 'while true; do date; sleep 1; done'`

>Polecenie: `docker logs -f looper` 

![Screenshoot 04](scr04.png)

>Polecenie: `docker pause looper` 

>Polecenie: `docker unpause looper` 

![Screenshoot 05](scr05.png)

>Polecenie: `docker attach looper` 

![Screenshoot 06](scr06.png)

>Polecenie: `docker attach --no-stdin looper` 

![Screenshoot 07](scr07.png)

### Uruchamianie procesów w kontenerze za pomocą docker exec

>Polecenie: `docker exec looper ls -la` 

![Screenshoot 08](scr08.png)

>Polecenie: `docker exec -it looper bash` 

![Screenshoot 09](scr09.png)

>Polecenie: `docker kill looper` 

>Polecenie: `docker rm looper`

![Screenshoot 10](scr10.png)

### Ćwiczenie 1.3

> Polecenie : `docker run --name task devopsdockeruh/simple-web-service:ubuntuimple-web-service:ubuntu`

> Polecenie :`docker exec -it task bash`

> Polecenie :`tail -f ./text.log`

![Screenshoot 11](scr11.png)


### Ubuntu w kontenerze to po prostu... Ubuntu
> Polecenie :`docker run -it ubuntu`

![Screenshoot 12](scr12.png)

> Polecenie :`apt-get update`

> Polecenie : `apt-get -y install nano`

> Polecenie : `cd tmp/`

> Polecenie : `nano temp_file.txt`

![Screenshoot 13](scr13.png)

![Screenshoot 14](scr14.png)

![Screenshoot 15](scr15.png)
![Screenshoot 16](scr16.png)

### Ćwiczenie 1.4

> Polecenie : `docker exec -it task2 bash`

> Polecenie : `sudo apt update`

> Polecenie : `sudo apt install curl`

> Polecenie : `docker run -it --name task2 ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'`

![Screenshoot 17](scr17.png)
![Screenshoot 18](scr18.png)
![Screenshoot 19](scr19.png)
