# Stage Setup

Polecenie 
```
git clone https://github.com/ibnesayeed/linkextractor.git
cd linkextractor
git checkout demo
```
![scr01](scr01.png)

# Step 0: Basic Link Extractor Script

Polecenie 
```
git checkout step0
tree

cat linkextractor.py

./linkextractor.py http://example.com/

ls -l linkextractor.py

python3 linkextractor.py
```

![scr02](scr02.png)

# Step 1: Containerized Link Extractor Script

Polecenie 
```
git checkout step1
tree

cat Dockerfile
```

![scr03](scr03.png)

> Polecenie : `docker image build -t linkextractor:step1 .`

![scr04](scr04.png)

> Polecenie : `docker image ls`

![scr05](scr05.png)


> Polecenie : `docker container run -it --rm linkextractor:step1 http://example.com/`

>Polecenie : `docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/`

![scr06](scr06.png)

# Step 2: Link Extractor Module with Full URI and Anchor Text

>Polecenie : `docker image build -t linkextractor:step2 .`

>Polecenie : `docker image ls`

![scr07](scr07.png)

>Polecenie : `docker container run -it --rm linkextractor:step2 https://training.play-with-docker.com/`

![scr08](scr08.png)

>Polecenie : `docker container run -it --rm linkextractor:step1 https://training.play-with-docker.com/`

![scr09](scr09.png)

# Step 3: Link Extractor API Service

>Polecenie : `docker image build -t linkextractor:step3 .`

![scr10](scr10.png)

Polecenie : 
```
docker container run -d -p 5000:5000 --name=linkextractor linkextractor:step3

docker container ls

curl -i http://localhost:5000/api/http://example.com/
```
![scr11](scr11.png)


Polecenie : 
```
docker container logs linkextractor

docker container rm -f linkextractor
```

![scr12](scr12.png)

# Step 4: Link Extractor API and Web Front End Services

> Polecenie : `docker-compose up -d --build`

![scr13](scr13.png)

> Polecenie : `docker container ls`

> Polecenie : `curl -i http://localhost:5000/api/http://example.com/`

![scr14](scr14.png)
![scr15](scr15.png)

> Polecenie : `sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php`

![scr16](scr16.png)

Polecenie:
```
git reset --hard

docker-compose down 
```

![scr17](scr17.png)

# Step 5: Redis Service for Caching

> Polecenie : `docker-compose up -d --build`

![scr18](scr18.png)


> Polecenie : `docker-compose exec redis redis-cli monitor`
![scr19](scr19.png)

> Polecenie : `sed -i 's/Link Extractor/Super Link Extractor/g' www/index.php`

![scr20](scr20.png)
*Brak zmian*

# Step 6: Swap Python API Service with Ruby

> Polecenie : `docker-compose up -d --build`

![scr21](scr21.png)

> Polecenie : `curl -i http://localhost:4567/api/http://example.com/`

![scr22](scr22.png)

![scr22](scr23.png)

> Polecenie : `docker-compose down`

> Polecenie : `cat logs/extraction.log`

![scr22](scr24.png)