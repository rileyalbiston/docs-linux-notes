# PostgrSQL on Ubuntu

## 1. Ubuntu

...

## 2. Install PostgreSQL

```
sudo apt-get update

sudo apt-get install postgresql postgresql-contrib
```

Switch to postgres account:

```
sudo -i -u postgres
```

To access the psql prompt:

```
psql
```

To quit psql prompt:

```
\q
```

To go straight to psql prmopt with switch accounts first:

```
sudo -u postgres psql
```

## 3. Create a New Database

With ```psql```:

```
CREATE DATABASE testdb;
```

Using ```sudo``` without switching to the ```postgres``` account:

```
sudo -u postgres createdb testdb
```

Or with being logged in with the ```postgres``` account:

```
createdb testdb
```

## 4. Create New User and Give Access to New Database

With ```psql```:

```
CREATE USER testuser WITH PASSWORD 'password';
```

Using ```sudo``` without switching to the ```postgres``` account:

```
sudo -u postgres createuser --interactive
```

Or with being logged in with the ```postgres``` account:

```
createuser --interactive
```

### Grant Privliages to the New User

[privileges](https://www.postgresql.org/docs/9.0/privileges.html)

[grant](https://www.postgresql.org/docs/9.0/sql-grant.html)

With ```psql```:

```
GRANT ALL ON testdb TO testuser;
```

```
```




NOTES:

Roles:

Admin Role:

CREATE ROLE testadmin WITH CREATEDB CREATEROLE LOGIN ENCRYPTED PASSWORD 'password';

User Role:

CREATE ROLE testuser WITH LOGIN ENCRYPTED PASSWORD 'password';

Users:

CREATE ROLE user1 WITH LOGIN ENCRYPTED PASSWORD 'password' INHERIT;
GRANT testuser to user1;
CREATE ROLE user2 WITH LOGIN ENCRYPTED PASSWORD 'password' INHERIT;
GRANT testuser to user1;

--CREATE USER testuser WITH ENCRYPTED PASSWORD 'password';--
GRANT ALL PRIVILEGES ON DATABASE testdb TO testuser; <-- can't query

GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO testuser; <-- can't query


## On test_db

GRANT SELECT ON day TO testuser;
GRANT SELECT ON day TO testadmin;


ALTER TABLE testtable OWNER TO testuser;



Login from windows:

psql postgresql://user1:password@127.0.0.1:5432/test_db 
psql postgresql://testuser:password@127.0.0.1:5432/test_db 
psql postgresql://testadmin:password@127.0.0.1:5432/test_db



psql postgresql://testuser:password@192.168.1.178:5432/testdb