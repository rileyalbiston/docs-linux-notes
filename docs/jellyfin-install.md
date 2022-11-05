# Jellyfin install on Linux Mint

| **Date:** 05 Oct 2022 |
| **OS:** Linux Mint 20.2 |

[https://jellyfin.org/docs/general/administration/installing.html#ubuntu](https://jellyfin.org/docs/general/administration/installing.html#ubuntu) 

[https://www.how2shout.com/linux/how-to-install-jellyfin-media-server-on-ubuntu-22-04-lts/](https://www.how2shout.com/linux/how-to-install-jellyfin-media-server-on-ubuntu-22-04-lts/)

```bash
sudo rm /etc/apt/trusted.gpg.d/debian-jellyfin.gpg
sudo rm /etc/apt/trusted.gpg.d/jellyfin.gpg
sudo rm /etc/apt/sources.list.d/jellyfin.list
```

```bash
echo "deb [arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/jellyfin.list
```

The scripts given genrally use a automatically detect the version of Ubuntu being used. As this is on Mint that causes the install to fail. 

The below is used to work out which version of Mint is being run and which version of Ubuntu it's based on so it can be hard coded into the install command.

```bash
riley@IronG:~$ cat /etc/issue
Linux Mint 20.2 Uma \n \l



riley@IronG:~$ hostnamectl
   Static hostname: IronG
         Icon name: computer-desktop
           Chassis: desktop
        Machine ID: dafd9a61376b4676aa8b190bc1ed4b43
           Boot ID: a7a0a0b64e8c494fad6d0296ef5ec73b
  Operating System: Linux Mint 20.2
            Kernel: Linux 5.4.0-109-generic
      Architecture: x86-64


riley@IronG:~$ cat /etc/upstream-release/lsb-release 
DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=20.04
DISTRIB_CODENAME=focal
DISTRIB_DESCRIPTION="Ubuntu Focal Fossa"
```

```bash
sudo rm /etc/apt/sources.list.d/jellyfin.list
```

```bash
curl -fsSL https://repo.jellyfin.org/ubuntu/jellyfin_team.gpg.key | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/debian-jellyfin.gpg

echo "deb [arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/ubuntu focal main" | sudo tee /etc/apt/sources.list.d/jellyfin.list

sudo apt update

sudo apt install jellyfin
```


