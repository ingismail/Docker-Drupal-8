Commands to know
---

```sh
# getting the list of the images
$ docker images
#REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
#hello-docker        latest              3dcf8710657f        4 minutes ago       402.6 MB
#php                 7.0-apache          336e2be8a343        2 weeks ago         402.6 MB

# getting the list of the images IDs only
$ docker images -q
#3dcf8710657f
#336e2be8a343

# getting the list of containers (active and non active containers)
$ docker ps -a

# getting the list of containers IDs (active and non active containers)
$ docker ps -a -q

# getting the list of containers (active only)
$ docker ps

# deleting an image
$ docker rmi <image-id>

# deleting an container
$ docker rm <container-id>
```
