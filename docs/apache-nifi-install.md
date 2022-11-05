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