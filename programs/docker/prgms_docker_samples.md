# Samples

## 1. Get a python image

```bash
$ docker pull python
```

## 2. Use fjsbox : A fullstack javascript docker image

Developping fullstack js client/server application with this simple Docker image, based on [nodejs](https://registry.hub.docker.com/_/node/).

* Start the container \(image will be pulled if it's the first time\)

```bash
$ sudo docker run -it --rm -v /home/me/myproject:/app -p 3000:3000 mikamboo/devbox
```

* Play with the box ...

