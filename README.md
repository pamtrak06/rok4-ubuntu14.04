# What is rok4 ?

"ROK4 est un serveur open-source (sous licence CeCILL-C) écrit en C++ permettant la diffusion de données images géo-référencées. Développé par les équipes du projet Géoportail de l’Institut National de l’Information Géographique et Forestière, il implémente les standards ouverts de l’Open Geospatial Consortium (OGC) WMS 1.3.0 et WMTS 1.0.0."

> [Source : http://www.rok4.org/ ](http://www.rok4.org/)

![logo](http://www.rok4.org/wp-content/uploads/2012/12/logo_rok4.png)

# How to use this image

## Build rok4 docker image

This image is built under ubuntu 14.04.
```
docker build -t pamtrak06/rok4-ubuntu14.04:latest https://raw.githubusercontent.com/pamtrak06/rok4-ubuntu14.04/master/Dockerfile
```

## Run rok4 docker container

Boot docker
```
$ boot2docker start
```

Run container
```
$ docker run -it -p 80:80 -p 22:22 pamtrak06/rok4-ubuntu14.04
```

Exit container without stop it
```
CTRL+P  &  CTRL+Q
```

Open a terminal session on a running container
```
$ docker exec -i -t pamtrak06/rok4-ubuntu14.04 /bin/bash
```

Get docker vm ip : 
```
$ boot2Docker ip => 192.168.59.103
```

## Configure rok4 server
