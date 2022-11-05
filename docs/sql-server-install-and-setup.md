# Databases: SQL Server on  Ubuntu

[SQLShack - How to install SQL Server on Ubuntu](https://www.sqlshack.com/how-to-install-sql-server-on-ubuntu/)

[MS Docs install SQL Server](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver15)



## Install SQL Server

1.

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
```

2.

```bash
sudo add-apt-repository "$(wget -qO- https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2019.list)"
```

3.

```bash
sudo apt-get update
sudo apt-get install -y mssql-server
```

4.

```bash
sudo /opt/mssql/bin/mssql-conf setup
```

Edition: Developer

SA password: Password123   (Dell Opitplex with Linux Mint)



5.

```bash
systemctl status mssql-server --no-pager
```

6. If you plan to connect remotely, you might also need to open the SQL Server TCP port (default 1433) on your firewall.

Check firewall:

```bash
sudo ufw status verbose
```

Open port:

```bash
sudo ufw allow 1433/tcp
```



##  Install the SQL Server command-line tools

1.

```bash
sudo apt-get update 
sudo apt install curl
```

2.

```bash
curl https://packages.microsoft.com/config/ubuntu/20.04/prod.list | sudo tee /etc/apt/sources.list.d/msprod.list
```

3.

```bash
sudo apt-get update 
sudo apt-get install mssql-tools unixodbc-dev
```

4.

```bash
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
```

aaa

```bash
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
source ~/.bashrc
```



## Connect locally

aa

```bash
sqlcmd -S localhost -U sa -P '<YourPassword>'
```

## Connect over local network

Check for ip address:

```bash
hostname -I
```





**Can also connect through SSMS from Windows 10**

Connect from remote computer (running Windows 10):

sqlcmd -S [Servername where SQL Installed], [Port Number ] \ [SQL Server instance name] -U [Username] -P [Password]

```bash
sqlcmd -S 192.168.0.11,1433\MSSQLSERVER -U sa -P Password123
```

