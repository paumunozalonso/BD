# Instal·lació

Descarreguem la clau GPG de Microsoft des del servidor i l'exportem a un arxiu.

```curl -fsSL https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-prod.gpg ```

Movem l'arxiu anterior a la carpeta on APT busca les claus de confiança dels repositoris.

```sudo cp /usr/share/keyrings/microsoft-prod.gpg  /etc/apt/trusted.gpg.d/ ```


```curl -fsSL https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list | sudo tee /etc/apt/sources.list.d/mssql-server-2022.list```


```sudo apt-get update```


```sudo apt-get install -y mssql-server```


```sudo /opt/mssql/bin/mssql-conf setup```


```systemctl status mssql-server --no-pager```


```curl https://packages.microsoft.com/config/ubuntu/22.04/prod.list | sudo tee /etc/apt/sources.list.d/mssql-release.list```


```sudo apt-get update ```


```sudo apt-get install mssql-tools18 unixodbc-dev ```


```sqlcmd -S localhost -U sa -P 'P@ssw0rd!' ```


```SELECT name FROM master.dbo.sysdatabases ```


```sudo ufw allow 1433 ```


# Videoinstal·lació

[Instal·lació via terminal]( https://asciinema.org/a/VzjwT4jeIrALCy2HiUl0adpQ5)
>Avançar des del segon 15 fins al minut 9:57 a causa d'un bug de gravació
