# Use the official Azure SQL Edge image from Microsoft
FROM mcr.microsoft.com/azure-sql-edge

# Set environment variables
ENV ACCEPT_EULA=Y
ENV MSSQL_SA_PASSWORD=MY_STRONG_Password10!

# Expose the SQL Server port
EXPOSE 1433

# Run with SYS_PTRACE capability
CMD ["--cap-add", "SYS_PTRACE"]

# CMD ["additional-command"]  # Si es necesario agregar comandos adicionales

# Puedes agregar comandos adicionales si es necesario

# Ejemplo: Copiar scripts SQL a una ubicación específica
# COPY ./scripts /scripts

# Ejemplo: Ejecutar un script SQL durante la construcción
# RUN /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P $MSSQL_SA_PASSWORD -d master -i /scripts/setup.sql
