## Azure SQL Edge

#### Image
```sh
docker pull mcr.microsoft.com/azure-sql-edge
```

#### Run Image
```sh
docker run --cap-add SYS_PTRACE -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=MY_STRONG_Password10!' -p 1433:1433 --name azuresqledge -d mcr.microsoft.com/azure-sql-edge
```

#### Run Imagen Premium (You need to pay)
```sh
docker run --cap-add SYS_PTRACE -e 'ACCEPT_EULA=1' -e 'MSSQL_SA_PASSWORD=MY_STRONG_Password10!' -e 'MSSQL_PID=Premium' -p 1433:1433 --name azuresqledge -d mcr.microsoft.com/azure-sql-edge
```


## Configure Image with Dockerfile

##### 1. Build Image
```sh
docker build -t tu-nombre-de-imagen:etiqueta .
```

##### 2. Start Image
```sh
docker run -p 1433:1433 --name azuresqledge -d tu-nombre-de-imagen:etiqueta
```

## Build Container
```sh
docker compose up
```