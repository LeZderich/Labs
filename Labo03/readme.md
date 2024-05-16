# Labo03 - Run a first container

## Pedagogical intent

In this lab, you'll:

* Get to grips with the first Docker commands,
* Run your first Docker
* Familiarize yourself with port publishing

---

Note: the docker engine must be running

## Task 01 - Get to grips with the first Docker commands

* List all images present on your installation

[INPUT]
```bash
docker images
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker images
REPOSITORY           TAG       IMAGE ID       CREATED         SIZE
sail-8.2/app         latest    821888db69dc   9 days ago      998MB
<none>               <none>    8dc71831ee38   9 days ago      998MB
mysql/mysql-server   8.0       1d9c2219ff69   16 months ago   496MB
PS C:\Users\phili\IdeaProjects\Labs> 
```

* Get the official Nginx image using this command

[INPUT]
```bash
docker pull nginx
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker pull nginx
Using default tag: latest
latest: Pulling from library/nginx
09f376ebb190: Pulling fs layer                                                                                                                                                                                                      
a11fc495bafd: Pull complete
933cc8470577: Pull complete
999643392fb7: Pull complete
971bb7f4fb12: Pull complete
45337c09cd57: Pull complete
de3b062c0af7: Pull complete
Digest: sha256:a484819eb60211f5299034ac80f6a681b06f89e65866ce91f356ed7c72af059c
Status: Downloaded newer image for nginx:latest
docker.io/library/nginx:latest

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview nginx
PS C:\Users\phili\IdeaProjects\Labs>
```

Note : do you see the different layer uploaded ?

* List -again- all image present on your installation

[INPUT]
```bash
docker images
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker images    
REPOSITORY           TAG       IMAGE ID       CREATED         SIZE
sail-8.2/app         latest    821888db69dc   9 days ago      998MB
<none>               <none>    8dc71831ee38   9 days ago      998MB
nginx                latest    e784f4560448   12 days ago     188MB
mysql/mysql-server   8.0       1d9c2219ff69   16 months ago   496MB
PS C:\Users\phili\IdeaProjects\Labs> 
```

Note : 188 MB is the size of your image... check it.

* List -again- all image present on your installation

[INPUT]
```bash
docker images
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker images    
REPOSITORY           TAG       IMAGE ID       CREATED         SIZE
sail-8.2/app         latest    821888db69dc   9 days ago      998MB
<none>               <none>    8dc71831ee38   9 days ago      998MB
nginx                latest    e784f4560448   12 days ago     188MB
mysql/mysql-server   8.0       1d9c2219ff69   16 months ago   496MB
PS C:\Users\phili\IdeaProjects\Labs> 
```

* List all Docker

[INPUT]
```
docker ps -a
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker ps -a
CONTAINER ID   IMAGE                    COMMAND                  CREATED      STATUS                    PORTS                                                    NAMES
6bdd939cdd92   sail-8.2/app             "start-container"        9 days ago   Exited (0) 39 hours ago                                                            matuxor-laravel.test-1
86b77e207751   mysql/mysql-server:8.0   "/entrypoint.sh mysq…"   9 days ago   Exited (0) 39 hours ago                                                            matuxor-mysql-1
62288c5d5c1c   sail-8.2/app             "start-container"        9 days ago   Exited (255) 9 days ago   0.0.0.0:5173->5173/tcp, 8000/tcp, 0.0.0.0:8080->80/tcp   005cd0e28b0f5c6c6de83c34a0db07948092881fd759eea2707004691cac7c49-laravel.test-1
2d6cfef8e1f0   mysql/mysql-server:8.0   "/entrypoint.sh mysq…"   9 days ago   Exited (255) 9 days ago   33060-33061/tcp, 0.0.0.0:3307->3306/tcp                  005cd0e28b0f5c6c6de83c34a0db07948092881fd759eea2707004691cac7c49-mysql-1
PS C:\Users\phili\IdeaProjects\Labs> 
```

## Task 02 - Run the container

* Run Nginx Docker

[INPUT]
```
docker run nginx
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker run nginx   
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2024/05/16 06:20:47 [notice] 1#1: using the "epoll" event method
2024/05/16 06:20:47 [notice] 1#1: nginx/1.25.5
2024/05/16 06:20:47 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14)
2024/05/16 06:20:47 [notice] 1#1: OS: Linux 5.15.146.1-microsoft-standard-WSL2
2024/05/16 06:20:47 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2024/05/16 06:20:47 [notice] 1#1: start worker processes
2024/05/16 06:20:47 [notice] 1#1: start worker process 29
2024/05/16 06:20:47 [notice] 1#1: start worker process 30
2024/05/16 06:20:47 [notice] 1#1: start worker process 31
2024/05/16 06:20:47 [notice] 1#1: start worker process 32
2024/05/16 06:20:47 [notice] 1#1: start worker process 33
2024/05/16 06:20:47 [notice] 1#1: start worker process 34
2024/05/16 06:20:47 [notice] 1#1: start worker process 35
2024/05/16 06:20:47 [notice] 1#1: start worker process 36
2024/05/16 06:20:47 [notice] 1#1: start worker process 37
2024/05/16 06:20:47 [notice] 1#1: start worker process 38
2024/05/16 06:20:47 [notice] 1#1: start worker process 39
2024/05/16 06:20:47 [notice] 1#1: start worker process 40
2024/05/16 06:20:47 [notice] 1#1: start worker process 41
2024/05/16 06:20:47 [notice] 1#1: start worker process 42
2024/05/16 06:20:47 [notice] 1#1: start worker process 43
2024/05/16 06:20:47 [notice] 1#1: start worker process 44

Not Wroking, i can't reach the webpage
```

* I had to run the app with:

```bash
docker run -d -p 8080:80 nginx # to specify the port 80.
```

* Can you reach the default page of nginx

Note : By default, Nginx is listening on port 80

[INPUT]
```
curl localhost
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> curl localhost


StatusCode        : 200
StatusDescription : OK
Content           : <!DOCTYPE html>
                    <html>
                    <head>
                    <title>Welcome to nginx!</title>
                    <style>
                    html { color-scheme: light dark; }
                    body { width: 35em; margin: 0 auto;
                    font-family: Tahoma, Verdana, Arial, sans-serif; }
                    </style...
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    Accept-Ranges: bytes
                    Content-Length: 615
                    Content-Type: text/html
                    Date: Thu, 16 May 2024 06:30:40 GMT
                    ETag: "661e8b67-267"
                    Last-Modified: Tue, 16 Apr 2024 ...
Forms             : {}
Headers           : {[Connection, keep-alive], [Accept-Ranges, bytes], [Content-Length, 615], [Content-Type, text/html]...}
Images            : {}
InputFields       : {}
Links             : {@{innerHTML=nginx.org; innerText=nginx.org; outerHTML=<A href="http://nginx.org/">nginx.org</A>; outerText=nginx.org; tagName=A; href=http://nginx.org/}, @{innerHTML=nginx.com; innerText=nginx.com;
                    outerHTML=<A href="http://nginx.com/">nginx.com</A>; outerText=nginx.com; tagName=A; href=http://nginx.com/}}
ParsedHtml        : System.__ComObject
RawContentLength  : 615
```

* Stop this first attempt

[INPUT]
```
docker stop <id>

docker stop d3eadcbd0ab3a1626d454f572b5e966bd34f1d32c55f9cd4773f27add8bba411
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker stop d3eadcbd0ab3a1626d454f572b5e966bd34f1d32c55f9cd4773f27add8bba411
d3eadcbd0ab3a1626d454f572b5e966bd34f1d32c55f9cd4773f27add8bba411
PS C:\Users\phili\IdeaProjects\Labs>
```

## Task 03 - Familiarize yourself with port publishing

* Make it possible to reach nginx with this command

[Publish a port](https://docs.docker.com/network/#published-ports)

[INPUT]
```
curl localhost:8080

# I Had to use 
docker run -d -p 8080:80 nginx
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> curl http://localhost:8080    


StatusCode        : 200
StatusDescription : OK
Content           : <!DOCTYPE html>
                    <html>
                    <head>
                    <title>Welcome to nginx!</title>
                    <style>
                    html { color-scheme: light dark; }
                    body { width: 35em; margin: 0 auto;
                    font-family: Tahoma, Verdana, Arial, sans-serif; }
                    </style...
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    Accept-Ranges: bytes
                    Content-Length: 615
                    Content-Type: text/html
                    Date: Thu, 16 May 2024 06:35:30 GMT
                    ETag: "661e8b67-267"
                    Last-Modified: Tue, 16 Apr 2024 ...
Forms             : {}
Headers           : {[Connection, keep-alive], [Accept-Ranges, bytes], [Content-Length, 615], [Content-Type, text/html]...}
Images            : {}
InputFields       : {}
Links             : {@{innerHTML=nginx.org; innerText=nginx.org; outerHTML=<A href="http://nginx.org/">nginx.org</A>; outerText=nginx.org; tagName=A; href=http://nginx.org/}, @{innerHTML=nginx.com; innerText=nginx.com;
                    outerHTML=<A href="http://nginx.com/">nginx.com</A>; outerText=nginx.com; tagName=A; href=http://nginx.com/}}
ParsedHtml        : System.__ComObject
RawContentLength  : 615
```

* Stop and delete the container

[INPUT]
```
docker stop c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221

docker rm c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker stop c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221
c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221
PS C:\Users\phili\IdeaProjects\Labs> docker rm c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221
c473394121ec51ac5ac89e094b3672e2b003d367effe617730c5739654889221
PS C:\Users\phili\IdeaProjects\Labs> 
```

* Delete the image

[INPUT]
```
docker rmi nginx
```

[OUTPUT]
```
PS C:\Users\phili\IdeaProjects\Labs> docker rmi nginx
Untagged: nginx:latest
Untagged: nginx@sha256:a484819eb60211f5299034ac80f6a681b06f89e65866ce91f356ed7c72af059c
Deleted: sha256:e784f4560448b14a66f55c26e1b4dad2c2877cc73d001b7cd0b18e24a700a070
Deleted: sha256:38ecd4de01b55beb32c596678b061db27f8ecb586096f031e4553869e52a1dc2
Deleted: sha256:168e1116c229abdf6cd9c0f07f82d40d53e358b1da4e1242a15101ece28ccb28
Deleted: sha256:0b7dc712f354a2312c1f1bb6380d8e23919baf0cc09f32a5a4595afb6c3a440b
Deleted: sha256:3ecb32a94af1f9a46cc259bf6cc677acd1fef2023f746e973862d1a8c9e31fe3
Deleted: sha256:b4c8fa0ae3e9f4f7d0ee49a9ac13d8aebd6f2d4a53e204e75f74e4bcb143132f
Deleted: sha256:cd5b03306052e1a435b98a34cd2579dc48f8f0ca280a147f19f066ddb6a0b81d
Deleted: sha256:5d4427064ecc46e3c2add169e9b5eafc7ed2be7861081ec925938ab628ac0e25
PS C:\Users\phili\IdeaProjects\Labs> 
```
