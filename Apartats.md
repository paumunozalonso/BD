***Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa realitza aquesta tasca? Realitza una securització de la instal·lació.***

Per realitzar una protecció de la instal·lació podem utilitzar SQL Server Configuration Manager, ja que aquesta eina permet configurar diversos apartats de seguretat com l'autentificació, permisos d'accés, dades xifrades...  

Per exemple, podem configurar els permisos dels rols, grups, usuaris...
![Captura](/../images/seguretat.png)  

Una altra mesura de seguretat és la configuració i visualització dels logs.
![Captura](/../images/seguretat2.PNG)    

![Captura](/../images/seguretat3.PNG)  

Cal destacar també l'autentificació per poder accedir al servidor.

![Captura](/../images/seguretat4.PNG) 

I per acabar també podem veure la configuració de les polítiques i certificats entre altres mesures.

![Captura](/../images/seguretat5.PNG) 


***Quines són les instruccions per arrancar / verificar status / apagar servei de la base de dades del SBGB escollit a nivell sistema operatiu?***

Arrancar: systemctl start mssql-server    
Verificar status: systemctl status mssql-server    
Apagar servei: systemctl stop mssql-server  


***A on es troba i quin nom rep el fitxer de configuració del SGBD escollit?***

/opt/mssql/bin/mssql-conf

***A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?***

/var/opt/mssql/data

![Captura](/../images/SQL.PNG)

***El servei de SGBD escollit en quins ports escolta. Quina modificació/passos caldrien fer per canviar aquest port a un altre per exemple? Important: No realitzis els canvis. Només indica els passos que faries.***

Editem el fitxer de configuració indicant el nou port

```sudo /opt/mssql/bin/mssql-conf set network.tcpport <new_tcp_port>```

Reiniciem el servei

```sudo systemctl restart mssql-server```

Provem a accedir a la base de dades amb el nou port

```sqlcmd -S localhost,<new_tcp_port> -U test -P test ```

***Incloure en la documentació un petit apartat a on s'expliqui com realitzar la connexió a la BD. Demostra que us podeu connectar al SGBD a través d’una eina de gestió de BD o  a través d’un programa.***

[Demostració](https://drive.google.com/file/d/1IfvtZyMmU2-tuAvv9whRb3NrH3jyleNd/view?usp=sharing )

***Quin tipus de SGBD? (Relacional, no relacional, graf, document,....)***

És un sistema relacional, que està dissenyat per gestionar i relacionar dades estructurades.
