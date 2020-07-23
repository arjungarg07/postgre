
# PostgreSQL
Source: [Tableplus](https://tableplus.com/blog/2018/10/how-to-start-stop-restart-postgresql-server.html).
Another very good documentation to consider:
From [NTU](https://www3.ntu.edu.sg/home/ehchua/programming/sql/PostgreSQL_GetStarted.html#:~:text=for%20the%20password.-,4.4%20Add%20your%20UNIX%20user%20as%20PostgreSQL%20user,%22%20su%20%2D%20username%20%22)
Another [Cheatsheet](https://video.udacity-data.com/topher/2019/August/5d5a1055_postgres-psql-cheat-sheet/postgres-psql-cheat-sheet.pdf)

  

## Update and install PostgreSQL 10.4

  

```
sudo apt-get update
sudo apt-get install postgresql-10.4
```

  

By default, the postgres user has no password and can hence only connect if ran by the postgres system user. The following command will assign it:

```
sudo -u postgres psql -c "ALTER USER postgres PASSWORD 'postgres';"
sudo -u postgres psql -c "CREATE DATABASE testdb;"
```

  

- Start the PostgreSQL server

  

```
sudo service postgresql start
```

  

- Stop the PostgreSQL server:

  

```
sudo service postgresql stop
```

  

## Postgres CLI tools

Keep this as a general reference. You'll be using these commands quite a lot if you are building web apps with Postgres.

  
```
### Log in as a particular user

Default installed user is called postgres i.e. you could initially login with 
```
sudo -u postgres -i
```
```
sudo -u <username> -i
```

e.g. sudo -u bob -i

  

### Create a new database

```
createdb <database_name>
```

e.g. createdb mydb

  

### Destroy a database

```
dropdb <database_name>
```

e.g. dropdb mydb

### Reset a database

```
dropdb <database_name> && createdb <database_name>
```

e.g. dropdb mydb && createdb mydb

  

Try it yourself!

Gain technical proficiency in managing postgres databases by practicing creating, dropping, and resetting databases. Do this in your terminal, if you successfully installed Postgres on your local computer, or interact with the terminal in this workspace below, which already has Postgres installed.

# Intro to psql
Postgres installation comes with an interactive terminal app called psql.

## Takeaways

-   **psql**  is an interactive terminal application for connecting and interacting with your  _local_  postgres server on your machine.
-   Connect using  `$ psql <dbname>`
-   psql lets you
    -   Directly type and execute SQL commands to your database
    -   Inspect and preview your database and database tables using psql meta-commands

##### Protip: type  `\?`  into psql to see a list of available commands

## Useful basic psql commands

`psql <dbname> [<username>]`

Starts psql with a connection to dbname. Optionally use another user than current user

In psql:

`# \l`

List all databases on the server, their owners, and user access levels

`# \c <dbname>`

Connect to a database named

`# \dt`

Show database tables

`# \d <tablename>`

Describe table schema

`# \q`

Quit psql, return to the terminal

`# \?`

Get help, see list of available commands
