# Install ACE Wiki

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

