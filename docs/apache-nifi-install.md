# Apache NiFi install on Linux Mint

| **Date:** 05 Oct 2022 |
| **OS:** Linux Mint 20.2 |

[https://www.tecmint.com/install-apache-nifi-in-ubuntu/](https://www.tecmint.com/install-apache-nifi-in-ubuntu/)

This link has been the best install guide:

[https://medium.com/gbtech/installing-apache-nifi-on-ubuntu-9bca3cfe65d0](https://medium.com/gbtech/installing-apache-nifi-on-ubuntu-9bca3cfe65d0)

tar file:

[https://archive.apache.org/dist/nifi/](https://archive.apache.org/dist/nifi/)

[https://archive.apache.org/dist/nifi/1.13.2/](https://archive.apache.org/dist/nifi/1.13.2/)


```bash
wget https://archive.apache.org/dist/nifi/1.13.2/nifi-1.13.2-bin.tar.gz
```

Check java version

```bash
java -version
```



## Set java home

[https://vitux.com/how-to-setup-java_home-path-in-ubuntu/](https://vitux.com/how-to-setup-java_home-path-in-ubuntu/)

```bash
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
```


## Open in browser

[http://localhost:8080/nifi/](http://localhost:8080/nifi/)



## Getting NiFi to work over local network

By default NiFi was only running using localhost.

To access it over the local network it needs to be set to access using the host machines IP address.

This setting is changes in the `nifi.properites` file. 

It is located in:

```bash
opt/nifi-1.13.2/conf/
```

Change:

```
# web properties #
#############################################

# For security, NiFi will present the UI on 127.0.0.1 and only be accessible through this loopback interface.
# Be aware that changing these properties may affect how your instance can be accessed without any restriction.
# We recommend configuring HTTPS instead. The administrators guide provides instructions on how to do this.

nifi.web.http.host=127.0.0.1
nifi.web.http.port=8080
nifi.web.http.network.interface.default=
```

To:

```
# web properties #
#############################################

# For security, NiFi will present the UI on 127.0.0.1 and only be accessible through this loopback interface.
# Be aware that changing these properties may affect how your instance can be accessed without any restriction.
# We recommend configuring HTTPS instead. The administrators guide provides instructions on how to do this.

nifi.web.http.host=192.168.1.221
nifi.web.http.port=8080
nifi.web.http.network.interface.default=
```

**Allow through firewall**

```bash
sudo ufw allow 8080
```

then

```bash
sudo ufw reload
```





