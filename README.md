# spring-boot-security

## Description
Spring boot authentication app with JWT and Spring Security.

## Usage

### API endpoints:
/api/signup

/api/signin

/api/test/all - retrieve public content

/api/test/user - access user's content

/api/test/mod - access moderator's content

/api/test/admin - access admin's content


### Run backend:
``` bash
mvn spring-boot:run
```

## Installation
run postgres image:
``` bash
docker run --name postgres-auth-db -e POSTGRES_PASSWORD=veryweakpassword -d -p 5432:5432 postgres:alpine
```

login to postgress command line:
``` bash
psql -U postgres
```

create the database inside the postgres container and postgres command line:
``` sql
CREATE DATABASE postgresauthdb;
```

After app started once, you can check that the tables got created in postgres command line:
``` bash
\c postgresauthdb

\d
```

*add the neede roles:*
``` sql
INSERT INTO roles(name) VALUES('ROLE_USER');

INSERT INTO roles(name) VALUES('ROLE_MODERATOR');

INSERT INTO roles(name) VALUES('ROLE_ADMIN');
```

check the ip:
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' postgres-auth-db