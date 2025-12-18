# Sekcja 5

### Interakcja z kontenerem przez wolumeny i porty

> Polecenie : `$ docker run -v "$(pwd):/mydir" yt-dlp https://www.youtube.com/watch?v=DptFY_MszQs`

![Screenshot 1](scr01.png)


### Ćwiczenie 1.9

> Polecenie: `touch text.log`

> Polecenie: `docker run --rm -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service`

[Plik logu](text.log)

![Screenshot 2](scr02.png)

### Ćwiczenie 1.10
> Polecenie: `docker run -p 8080:8080 devopsdockeruh/simple-web-service server`

![Screenshot 3](scr03.png)


