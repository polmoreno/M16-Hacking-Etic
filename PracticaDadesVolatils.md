## Pràctica Anàlisi de dades volàtils

## Index de continguts

1. Introducció
2. Anàlisi de connexions
3. Anàlisi d'usuaris
4. Anàlisi de serveis
5. Anàlisi de memòria
6. Linux

## 1

## Introducció

En aquesta pràctica realitzarem un anàlisi de les màquines en viu, es a dir, encesses, i observarem quins processos hi han corrent. Per això farem servir:

```
La suite SysInternals, de microsoft, per coneixer quins son els processos que estàn corrent.
MDD, per fer volcats de la memoria RAM Volatility, per analtizarel volcat fet previament.
```

## 2

## Análisis de conexions

● Obrim la consola de windows
```
C:\Windows\System32\cmd.exe
```

● Ports i connexions oberts:
```
netstat -a
```

● Tràfic per procés:
```
netstat -b
```

● Estadístiques de connexions:
```
netstat -es
```

● Conexions de NetBIOS:
```
nbtstat -r
```

● Caché de NetBIOS:
```
nbtstat -c
```

● Configuración de la red:
```
route PRINT
```

● Interfaces de red:
```
ipconfig /all
```

● Recursos compartidos:
```
net SHARE
```

● Obre un navegador y una terminal de comandes.   
● Navega per les pàgines de “itb.cat” y comproba cóm la comanda “netstat –a” es va actualizant amb totes les noves connexions.

## 3

## Anàlisi d'usuaris

● Obrim una consola de Windows:
```
C:\Windows\System32\cmd.exe
```

● Usuaris de NetBIOS:
```
nbtstat -n
```

● Usuaris de recursos compartits:
```
net USERS
```

● Usuaris locals i remots:
```
[ruta]/SysinternalsSuite/PsLoggedon.exe
```

● SID de usuarios:
```
[ruta]/SysinternalsSuite /PsGetsid.exe
```

## 4

## Anàlisis de serveis

● Obrim una consola de Windows:
```
C:\Windows\System32\cmd.exe
```

● Serveis en execució:
```
[ruta]/SysinternalsSuite /PsService.exe
```

● Processos actius:
```
[ruta]/SysinternalsSuite /PsList.exe
```

● Events del sistema:
```
[ruta]/SysinternalsSuite /PsLoglist.exe
```

● Obrim Wordpad: Inicio > Wordpad: Executem psList.exe per comprobar el procés.

## 5

## Análisis de memoria

· Windows

```
Descarrega l'última versió de ftk imager, dumpit i volatility, investiga com obtenir la informació següent:
```

```
Realitza un volcat de la memoria sobre un arxiu(amb dumpit i ftk imager), pots obrir el teu compte de correu per investigarlo més endavant.
```

```
Anàlisis el volcat amb Volatility. (Per realitzar l'anàlisis ho farem més comodament en un sistema linux per no haber d'instal·lar python3 a windows)
```


1. Comprova la versió de volaitily  
![Alt Image](./Images/ImagesDadesVolatils/1.png)  

2. Obteniu informació de la imatge.  
![Alt Image](./Images/ImagesDadesVolatils/2.png)  

3. Veure llista de processos.  
![Alt Image](./Images/ImagesDadesVolatils/3.png)  

4. Filtreu la llista de processos cercant la paraula clau "firefox".  
![Alt Image](./Images/ImagesDadesVolatils/4.png)  

5. Trobeu tots els identificadors oberts per un procés existent.  
![Alt Image](./Images/ImagesDadesVolatils/5.png)  

6. Cerqueu identificadors de fitxers i filtreu per tipus.  
![Alt Image](./Images/ImagesDadesVolatils/6.png)  

7. Volca un fitxer d'un procés existent a l'adreça virtual.  
![Alt Image](./Images/ImagesDadesVolatils/7.png)  

8. Volca tots els fitxers associats amb un PID existent.  
![Alt Image](./Images/ImagesDadesVolatils/8.png)  

9. Veure programes executats amb l'historial d'opcions d'ordres(cmd).  
![Alt Image](./Images/ImagesDadesVolatils/9.png)  

10. Veure connexions de xarxa actives i programes d'escolta.  
![Alt Image](./Images/ImagesDadesVolatils/10.png)  

11. Aboqueu els hash de contrasenya d'usuari de Windows.  
![Alt Image](./Images/ImagesDadesVolatils/11.png)  

12. Imprimiu el UserAssist del registre de Windows.  
![Alt Image](./Images/ImagesDadesVolatils/12.png)  

13. Llista tots els ruscs del registre de Windows disponibles a la memòria.  
![Alt Image](./Images/ImagesDadesVolatils/13.png)  

14. Imprimeix una clau específica del registre de Windows.  
![Alt Image](./Images/ImagesDadesVolatils/14.png)

15. Imprimeix una clau, subclaus i valors específics del Registre de Windows.  
![Alt Image](./Images/ImagesDadesVolatils/15.png)  

16. ¿Podries saber els comptes de correu oberts i la seva contrasenya?  
![Alt Image](./Images/ImagesDadesVolatils/16.png)  


## 6

## Linux

Ara, busca eines y métodes per realitzar la mateixa operativa amb Linux (Debian o
Ubuntu)


