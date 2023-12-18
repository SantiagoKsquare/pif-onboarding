In this step it is necessary to request access to the development environment database from the current Synkron environment manager.

Please have your public IP at hand, the easiest way to get it is to go to [whatismyip](https://www.whatismyip.com/)

Once access is granted, the next step is to open an ssh tunnel to the dev database. So request to the current Synkron environment manager for the key "kportal-dev.pem" and run the following command:

```
$ ssh -i "kportal-dev.pem" ubuntu@ec2-3-13-160-195.us-east-2.compute.amazonaws.com -fN -L 0.0.0.0:5432:127.0.0.1:5432
```

This command opens a tunnel to connect to the development database, now you can run the synkron api in your local environment using DB_HOST="localhost" in your .env and the following command:

```
npm run watch
```

# Connecting to local DB

In this step is necessary to have docker in your local environment.

[Postgres Docker image](https://hub.docker.com/_/postgres)
This command pull the postgres docker image

```
docker pull postgres
```

This command run the postgres docker container

```
docker run --name myPostgresDb -p 5455:5432 -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=Passw0rd -e POSTGRES_DB=appbackend -v /custom/mount:/var/lib/postgresql/data -d postgres
```

# Viewing data

You can use the database manager of your choice. We recommend [DBbeaver](https://dbeaver.io/) for its ease of use and powerful features.

# Next Topic

[Make my first update to the database schema](../db-migrations)
