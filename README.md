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


run mariadb image:
docker run --detach --name spring-security-mariadb --env MARIADB_USER=mariadb-user --env MARIADB_PASSWORD=my_cool_secret --env MARIADB_ROOT_PASSWORD=my-secret-pw  -p 3306:3306 mariadb:10.2

check the ip:
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' spring-security-mariadb