# SSH install on Linux Mint

| **Date:** 05 Oct 2022 |
| **OS:** Linux Mint 20.2 |

[https://linuxhint.com/enable-ssh-linux-mint/](https://linuxhint.com/enable-ssh-linux-mint/)

Check version:

```bash
ssh -V
```

If not installed, install with:

```bash
sudo apt install openssh-server
```

Check if SSH is enabled

```bash
sudo systemctl is-enabled ssh
```

If SSH is not enable, enable it

```bash
sudo systemctl enable ssh
```

And start SSH

```bash
sudo systemctl start ssh
```

Allow SSH through the firewall so it can be accessed over the local network

```bash
sudo ufw allow ssh
```

Reload the firewall so the new settings will take effect

```bash
sudo ufw reload
```

Now check the status of the firewall to make sure the changes have been made

```bash
sudo ufw status verbose
```