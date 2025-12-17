### Init your swarm

> Polecenie `docker swarm init --advertise-addr $(hostname -i)`

![scr01](scr01.png)
> Polecenie `docker swarm join --token SWMTKN-1-4t3wi1t6wp4b4l6x9zms903vvkglkihazrsl1uax6llf0xel1h-dgqq9lefbrxq2um9iyprb4wdy 192.168.0.29:2377)`

![scr08](scr08.png)
### Show members of swarm

> Polecenie `docker node ls`

![scr02](scr02.png)

### Clone the voting-app

Polecenie :
```
git clone https://github.com/docker/example-voting-app

cd example-voting-app
```

![scr03](scr03.png)

### Deploy a stack

> Polecenie `docker stack deploy --compose-file=docker-stack.yml voting_stack`

![scr04](scr04.png)

> Polecenie `docker stack ls`

![scr05](scr05.png)

> Polecenie `docker stack services voting_stack`

![scr06](scr06.png)

> Polecenie `docker stack ps voting_stack`

![scr07](scr07.png)

![scr09](scr09.png)

*Z 3 linków uruchamia sie tylko aplikacja do głosowania, swarm visualizer oraz result nie działają*