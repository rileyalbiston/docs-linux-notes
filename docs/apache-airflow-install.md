# Apache Airflow install on Linux Mint

| **Date:** 05 Oct 2022 |
| **OS:** Linux Mint 20.2 |


[Airflow Quick Start](https://airflow.apache.org/docs/apache-airflow/stable/start.html)

[Read the Docs](https://airflow.readthedocs.io/en/1.10.14/installation.html)

[https://unixcop.com/how-to-install-apache-airflow-on-ubuntu-20/](https://unixcop.com/how-to-install-apache-airflow-on-ubuntu-20/)

## Getting started


Run apt update and upgrade before getting started

```bash
sudo apt update -y && sudo apt upgrade -y
```

Airflow requires python so check what version is running
```bash
python3 -V
```

At the time I am running `Python 3.8.10`

Will need `pip` if it's not insralled.

```bash
sudo apt install python3-pip
```


Airflow needs a home. `~/airflow` is the default, but you can put it
somewhere else if you prefer (optional)

```bash
export AIRFLOW_HOME=~/airflow
```

## Option 1: Install Airflow using the constraints file

```bash
AIRFLOW_VERSION=2.4.0
PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)"
```

For example: 3.7

```bash
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt" 
```

For example: 

```bash
https://raw.githubusercontent.com/apache/airflow/constraints-2.4.0/constraints-3.7.txt
```

```bash
pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"
```

The Standalone command will initialise the database, make a user, and start all components for you.

```bash
airflow standalone
```

Visit `localhost:8080` in the browser and use the admin account details shown on the terminal to login.



Enable the example_bash_operator dag in the home page


## Option 2: Install Airflow with pip

```bash
sudo pip install 'apache-airflow[devel]'
```

```bash
sudo pip install "apache-airflow[postgres]==2.4.0" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.4.0/constraints-3.8.txt"
```

Once installed check Airflow version

```bash
airflow version
```

airflow initdbb < - command has been removed, use:

```bash
airflow db init
airflow db upgrade
```

Got loads of errors. Had to create a user first 

```bash
airflow users create --username admin --firstname admin --lastname admin --role Admin --email admin@admin.com
```

Then set the password

password: 336514


## Access Airflow in the browser

Starts apache airflow server by running the command below

```bash
airflow webserver -p 8081
```

My Airflow is running on port `8081` because NiFi is running on port `8080`.

Type the url below to open Airflow in a browser

[http://localhost:8081/home](http://localhost:8081/home)





### Check path

pip will most likely install Airflow to:

```bash
/usr/local/bin 
```

