### MariaDb Linux Mac
```sh
docker container run -dp 3306:3306 \
--name world-db \
--env MARIADB_USER=mariadb_user \
--env MARIADB_PASSWORD=mariadb_user \
--env MARIADB_ROOT_PASSWORD=root-mariadb-user \
--env MARIADB_DATABASE=world-db \
--volume world-db:/var/lib/mysql \
mariadb:jammy
```

### MariaDb Windows PowerShell
```sh
docker container run -dp 3306:3306 `
--name world-db `
--env MARIADB_USER=mariadb_user `
--env MARIADB_PASSWORD=mariadb_user `
--env MARIADB_ROOT_PASSWORD=root-mariadb-user `
--env MARIADB_DATABASE=world-db `
--volume world-db:/var/lib/mysql `
mariadb:jammy
```