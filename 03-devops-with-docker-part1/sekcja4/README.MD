# Sekcja 4

### Definiowanie warunków startowych kontenera

> Polecenie: `docker run -it ubuntu:22.04`

> Polecenie: `curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp` 


![Screenshot 1](scr01.png)

> Polecenie : `apt-get update && apt-get install -y curl`

![Screenshot 2](scr02.png)

> Polecenie: `curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp` 

![Screenshot 3](scr03.png)


> Polecenie: `chmod a+rx /usr/local/bin/yt-dlp` 

> Polecenie: `yt-dlp` 

![Screenshot 4](scr04.png)

> Polecenie: `apt-get install -y python3` 

![Screenshot 5](scr05.png)

[Dockerfile](Dockerfile.1)

> Polecenie: `docker build -f Dockerfile.1 -t yt-dlp .` 


> Polecenie: `docker run yt-dlp`

![Screenshot 6](scr06.png)

> Polecenie : `docker run yt-dlp https://www.youtube.com/watch?v=XsqlHHTGQrw`

![Screenshot 7](scr07.png)

> Polecenie : `docker run yt-dlp`


![Screenshot 8](scr08.png)

> Polecenie : `docker pull python:3.11`

![Screenshot 9](scr09.png)

> Polecenie : `docker run -it python:3.11`

![Screenshot 10](scr10.png)


> Polecenie : `docker run -it python:3.11 --version`

> Polecenie : `docker run -it python:3.11 bash`

![Screenshot 11](scr11.png)

> Polecenie : `docker container ls -a`

![Screenshot 12](scr12.png)

> Polecenie : `docker diff nervous_germain`
![Screenshot 13](scr13.png)

> Polecenie : `docker cp "nervous_germain://mydir/Linus Torvalds thinks Java is a horrible language [Aa55RKWZxxI].mp4" .`

![Screenshot 14](scr14.png)


### Ulepszony curler
[Skrypt](script.sh)

[Dockerfile](Dockerfile.3)

> Polecenie `docker build . -t curler-v2`

> Polecenie `docker run curler-v2 helsinki.fi`

![Screenshot 15](scr15.png)
