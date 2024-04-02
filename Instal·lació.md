# Instal·lació

Descarreguem la clau GPG de Microsoft des del servidor i l'exportem a un arxiu.

```curl -fsSL https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-prod.gpg ```

Movem l'arxiu anterior a la carpeta on APT busca les claus de confiança dels repositoris.

```sudo cp /usr/share/keyrings/microsoft-prod.gpg  /etc/apt/trusted.gpg.d/ ```

Afegim l'enllaç al repositori de paquets de Microsoft SQL Server 2022 a la llista de fonts de paquets APT.

```curl -fsSL https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list | sudo tee /etc/apt/sources.list.d/mssql-server-2022.list```

Actualitzem tots els paquets.

```sudo apt-get update```

Instal·lem el paquet del servidor SQL.

```sudo apt-get install -y mssql-server```

Executem la comanda per començar a configurar el servidor.

```sudo /opt/mssql/bin/mssql-conf setup```

Verifiquem l'estat del servidor.

```systemctl status mssql-server --no-pager```

Afegim aquest nou URL a la llista de fonts de paquets APT per a la instal·lació d'eines addicionals.

```curl https://packages.microsoft.com/config/ubuntu/22.04/prod.list | sudo tee /etc/apt/sources.list.d/mssql-release.list```

Tornem a actualitzar els paquets.

```sudo apt-get update ```

Instal·lem les eines de SQL Server i les llibreries de desenvolupament ODBC d'UNIX.

```sudo apt-get install mssql-tools18 unixodbc-dev ```

Una vegada tot funciona correctament, accedim al servidor.

```sqlcmd -S localhost -U sa -P 'P@ssw0rd!' ```

Comprovem que estan les bases de dades predeterminades.

```SELECT name FROM master.dbo.sysdatabases ```

Finalment, tot funciona correctament, per tant, una última configuració és habilitar el port 1433 perquè altres clients de fora es puguin connectar a la base de dades.

```sudo ufw allow 1433 ```


# Videoinstal·lació

[Instal·lació via terminal]( https://asciinema.org/a/VzjwT4jeIrALCy2HiUl0adpQ5)
>Avançar des del segon 15 fins al minut 9:57 a causa d'un bug de gravació
