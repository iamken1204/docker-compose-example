# Docker files
For development

## Note by __Kettan__
* To use a __mariadb__
1. Run:
```
$ docker-compose up -d mariadb
```
2. This container cannot be use while it is _"TERM environment variable not set."_ by default. [ref](https://github.com/dockerfile/mariadb/issues/3)
```
$ docker exec -it [mariadb-container-id] bash
$ export TERM=xterm
```
3. Done! Use your mariadb, Luke.

* ERROR: for data  Unknown runtime specified default && ERROR: Encountered errors while bringing up the project.
[ref](https://github.com/docker/docker/issues/24343)   
In docker version _1.12.0-rc3_ I encountered this bug, the solution is:   
1. Remove the old containers created by `docker-compose`.
```
$ docker-compose down -d
```
2. Recreate your belovely containers.
```
$ docker-compose up -d blahblahyourcontainer
```

## Services
* Mariadb
* Redis
* ElasticSearch

## Usage
### services
``` bash
docker-compose up -d redis mariadb elasticsearch
```

### node
``` bash
docker run -it --rm -v $(PWD):/workspace killtw/workspace node
```

### npm
``` bash
docker run -it --rm -v $(PWD):/workspace killtw/workspace npm
```

### bower
``` bash
docker run -it --rm -v $(PWD):/workspace killtw/workspace gulp
```

### gulp
``` bash
docker run -it --rm -v $(PWD):/workspace killtw/workspace gulp
```

## License

This is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
