### Start the Postgres

**Run your own local instance of Postgres. The best option is doing it using a Docker container.**

```
docker run \
 -dit \
 -v /tmp:/tmp \
 -e POSTGRES_USER=user \
 -e POSTGRES_DB=testdb \
 -e POSTGRES_PASSWORD=password \
 -p 5432:5432 \
 --name postgres postgres:11.4
```

You can test that your Postgres is running and accesible using psql:
```
docker exec -it postgres psql -d testdb -U user
psql (11.4 (Debian 11.4-1.pgdg90+1))
Type "help" for help.
```

Now write the command ```\l```
```
testdb=# \l
                               List of databases
   Name    |  Owner  | Encoding |  Collate   |   Ctype    |  Access privileges  
-----------+---------+----------+------------+------------+---------------------
 testdb   | user | UTF8     | en_US.utf8 | en_US.utf8 | 
 postgres  | user | UTF8     | en_US.utf8 | en_US.utf8 | 
 template0 | user | UTF8     | en_US.utf8 | en_US.utf8 | =c/user         +
           |         |          |            |            | user=CTc/user
 template1 | user | UTF8     | en_US.utf8 | en_US.utf8 | =c/user         +
           |         |          |            |            | user=CTc/user
(4 rows)


testdb=# 
```

### Connecting to PostgreSQL using pgAdming
PgAdmin is a suitable tool to admin and use Postgres. It can also be launched via docker.

```
docker run \
 -dit \
 --net=host \
 -v /tmp:/tmp \
 -p 80:80 \
 -e "PGADMIN_DEFAULT_EMAIL=pepe.sanchez@domain.ai" \
 -e "PGADMIN_DEFAULT_PASSWORD=xxx" \
 --name pgadmin dpage/pgadmin4
```

The use of the flat ```--net=host``` allows the container to use the same localhost than your machine. If you don't include it, localhost (127.0.0.1) will not be directly reachable.

Be sure that you set ```PGADMIN_DEFAULT_EMAIL``` and ```PGADMIN_DEFAULT_PASSWORD``` with more proper values.

Now you can access pgadmin using typing ```http://localhost/``` in your browser's address bar.
