# What is rok4 ?

"ROK4 est un serveur open-source (sous [licence CeCILL-C](http://www.cecill.info/licences/Licence_CeCILL-C_V1-fr.html)) écrit en C++ permettant la diffusion de données images géo-référencées. Développé par les équipes du projet Géoportail de l’Institut National de l’Information Géographique et Forestière, il implémente les standards ouverts de l’Open Geospatial Consortium (OGC) WMS 1.3.0 et WMTS 1.0.0."

> [Source : http://www.rok4.org/ ](http://www.rok4.org/)

![logo](http://www.rok4.org/wp-content/uploads/2012/12/logo_rok4.png)

# How to use this image

## Build rok4 docker image

This image is built under ubuntu 14.04.
```
docker build -t pamtrak06/rok4-ubuntu14.04 https://raw.githubusercontent.com/pamtrak06/rok4-ubuntu14.04/master/Dockerfile
```

## Run rok4 docker container

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

# Configure rok4 server

VirtualHost configuration

In the VirtualHost Apache2 configuration add the followings lines
```
ScriptAlias /fcgid/ /opt/rok4/bin/

<Directory "/opt/rok4/bin/">
SetHandler fcgid-script
Options +ExecCGI
AllowOverride None
Order allow,deny
Allow from all
</Directory>
```

For more information, see http://www.rok4.org/documentation

# Test services

WMS service is available from this url :
http://{docker ip}/fcgid/rok4?request=GetCapabilities&service=WMS

WMTS service is available from this url :
http://{docker ip}/fcgid/rok4?request=GetCapabilities&service=WMTS

# Licence

http://www.cecill.info/licences/Licence_CeCILL-C_V1-fr.html
