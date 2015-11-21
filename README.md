Run the container with the default values (uses as config /etc/ganglia/gmetad.conf):
```Shell
docker run -p 0.0.0.0:80:80 mbocek/ganglia
```
Run the container with separated coniguration on volume:
* create volume:
```Shell
docker run -d -v /etc/ganglia -v /var/lib/ganglia --name ganglia-data busybox true
```
* create container  
```Shell
docker run --name ganglia --volumes-from ganglia-data -p 0.0.0.0:80:9090 -p 8649:8649 -p 8649:8649/udp mbocek/ganglia
```

