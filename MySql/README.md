#### Image
```sh
docker pull mysql:5.7
```

#### Build Image
```sh
docker build -t name-image:tag .
```

#### Start Image
```sh
docker run -p 3306:3306 --name mariadb -d name-image:tag
```

#### Build Container
```sh
docker compose up
```
