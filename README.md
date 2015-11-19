Run the container with the default values (uses as config /etc/ganglia/gmetad.conf):
```Shell
docker run -p 0.0.0.0:80:80 mbocek/ganglia
```
Run the container with separated coniguration on volume:
* create volume:
```Shell
docker run -d -v /etc/ganglia -v /var/lib/ganglia -v /var/lib/ganglia-web --name data-ganglia busybox true
```
* create container  
```Shell
docker run --name ganglia --volumes-from data-ganglia -p 0.0.0.0:80:9090 mbocek/ganglia
```
