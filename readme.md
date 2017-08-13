# Docker image with Ruby

Base image with Ruby.

* Based on [https://github.com/phusion/passenger-docker](phusion image)

Contents
* rvm
* ruby




# Build

* build from github

```
docker build -t my-ruby github.com/maxivak/docker-base-ruby.git#master:version
```


## ruby 2.3.3

```
docker build -t my-ruby github.com/maxivak/docker-base-ruby.git#master:ruby23
```




# Examples

## basic

* build
```
docker build -t my-ruby github.com/maxivak/docker-base-ruby.git#master:ruby23
```

* run container
```
docker run -d --name my-container \
    my-ruby /sbin/my_init 
```

* connect to container
```
docker exec -ti my-container bash

# check rvm

rvm list


```
