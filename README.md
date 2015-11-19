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
docker run --name ganglia --volumes-from ganglia-data -p 0.0.0.0:80:9090 -p mbocek/ganglia
```

You should add gmetad.conf to /etc/ganglia i.e. via:
```Shell
docker run -it --volumes-from ganglia-data ubuntu
```
Content can looks like:
```Shell
data_source "my cluster" 50 localhost:8649
```

