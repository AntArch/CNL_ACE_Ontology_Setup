# Docker and ACE

# AceWiki

[Dr Tobias Kuhn](http://www.tkuhn.org/) developed AceWiki as part of his PhD. He's kindly [dockerised AceWiki](https://hub.docker.com/r/tkuhn/acewiki/).

* [docker cheat sheet](https://coderwall.com/p/2es5jw/docker-cheat-sheet-with-examples)
* [15 docker tips](http://sssslide.com/speakerdeck.com/bmorearty/15-docker-tips-in-5-minutes)

Initially one needs to *pull* the docker from the shared hub:

```docker
docker pull tkuhn/acewiki
```

then create a container:

```docker
docker run tkuhn/acewiki
```

Check out the container details

```docker
docker ps -all
```


http://172.17.0.3:9077/acewiki/

# AceRules

[Dr Tobias Kuhn](http://www.tkuhn.org/) developed AceRules as part of his PhD. He's kindly [dockerised AceRules](https://hub.docker.com/r/tkuhn/acerules/)


	
## Copying stuff to and from a docker instances

### copying **from** docker

docker cp <docker instance>:<source folder> <local target folder>

Examples:

To the current folder - 

> docker cp serene_boyd:/AceWiki/data .

To a specific folder
> docker cp serene_boyd:/AceWiki/data /home/beckant/delme/Grr

### copying **to** docker	

# More docker

docker pull tkuhn/acewiki
docker start tkuhn/acewiki
docker build tkuhn/acewiki
docker ps -a
docker images

## getting a bash shell into docker

docker start <docker instance>
docker exec -i -t <docker instance> /bin/bash

docker start serene_boyd
docker exec -i -t serene_boyd /bin/bash


