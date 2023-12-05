# Usa la imagen oficial de .NET 6.0 como base
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-env


# ENV PATH $PATH:/root/.dotnet/tools
# ENV PATH=$HOME/.dotnet/tools/:$PATH

# RUN dotnet tool install --global dotnet-ef --version 6.*

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Copia los archivos del proyecto y restaura las dependencias
COPY *.csproj ./
RUN dotnet restore

# Copia el resto de la aplicación y construye
COPY . ./
RUN dotnet publish -c Release -o out


# Establecer la imagen base para la aplicación final
FROM mcr.microsoft.com/dotnet/sdk:5.0

# Establecer el directorio de trabajo en /app
WORKDIR /app

# Copiar los archivos publicados de la compilación anterior
COPY --from=build-env /app/out .


# Expone el puerto en el que la aplicación escucha
EXPOSE 5000
EXPOSE 5001

RUN dotnet dev-certs https --trust

# Comando de inicio de la aplicación
ENTRYPOINT ["dotnet", "renombrar.dll"]