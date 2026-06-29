# Local Docker Validation for MS SQL database

This flow lets you validate database changes without installing SQL Server on your host.

## 1) Prerequisites

- Docker Desktop running
- Visual Studio Build Tools or Visual Studio with SSDT support
- SqlPackage available on PATH (or run it from its install folder) OR
- SqlPackage available in Docker container (see step 5)

## 2) Start SQL Server in Docker

inside the current folder run:

```powershell
docker compose up -d
```

Check container health:

```powershell
docker ps --filter "name=mydb-sql"
```

## 3) Build the SQL project

Build from Visual Studio by right-clicking on the project and selecting "Build" with *Release* configuration.

Expected output DACPAC:

- .\bin\Release\mydb.dacpac

## 4) Publish DACPAC to Docker SQL Server

In Visual Studio right-click the project and choose Publish.
In Target database connection:
Server name: localhost,14333
Authentication: SQL Server Authentication
User: sa
Password: your container password
Database: mydb_Local

## 5) Validate your changes

```cmd
docker exec -it mydb-sql /opt/mssql-tools18/bin/sqlcmd -C -No -U sa -P "YourPass"
> USE mydb_Local;SELECT * FROM <some-table> WHERE...;
> GO
> exit
```

## 6) Re-run quickly after changes

- Edit SQL files
- Run step 3
- Run step 4
- Run step 5

## 8) Stop and clean up

Stop container but keep data:

```powershell
docker compose down
```

Stop and remove data volume too:

```powershell
docker compose down -v
```
