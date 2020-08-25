
## httpd

```
$ cd httpd
$ docker build -t quay.io/swinches/httpd:latest .
$ docker push quay.io/swinches/httpd:latest
$ docker run -p 8080:80 -d --name httpd quay.io/swinches/httpd:latest
$ curl localhost:8080
<html><body><h1>It works!</h1></body></html>
$ docker exec -it httpd cat /logs/access_log
172.17.0.1 - - [25/Aug/2020:12:04:46 +0000] "GET / HTTP/1.1" 200 45 "-" "curl/7.64.1"
```

## Fluentd

```
$ cd fluentd
$ docker build -t quay.io/swinches/fluentd:latest .
$ docker push quay.io/swinches/fluentd:latest
```

## Filebeat

```
$ cd filebeat
$ docker build -t quay.io/swinches/filebeat:latest .
$ docker push quay.io/swinches/filebeat:latest
$ docker push quay.io/swinches/filebeat:latest
```

## Kubernetes logging with fluentd

```
oc create -f httpd-withfluentd.yml
oc expose svc/httpd
```


## Kubernetes logging with filebeat

```
oc create -f httpd-withfilebeat.yml
oc expose svc/httpd
```