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

En aquesta pràctica realitzarem un anàlisi de les màquines en viu, es a dir, encesses,
i observarem quins processos hi han corrent. Per això farem servir:

```
la suite SysInternals, de microsoft, per coenixer quins son els processos que
estàn corrent.
MDD, per fer volcats de la memoria RAM
Volatility, per analtizarel volcat fet previament.
```
## 2

## Análisis de conexions

```
Obrim la consola de windows
```
```
C:\Windows\System32\cmd.exe
```
```
Ports i connexions oberts:
```
```
netstat -a
```
```
Tràfic per procés:
```
```
netstat -b
```

```
Estadístiques de connexions:
```
```
netstat -es
```
```
Conexions de NetBIOS:
```
```
nbtstat -r
```
```
Caché de NetBIOS:
```
```
nbtstat -c
```
```
Configuración de la red:
```
```
route PRINT
```
```
Interfaces de red:
```
```
ipconfig /all
```
```
Recursos compartidos:
```
```
net SHARE
```
```
Obre un navegador y una terminal de comandes.
Navega per les pàgines de “itb.cat” y comproba cóm la comanda “netstat –a” es
va actualizant amb totes les noves connexions.
```
## 3

## Anàlisi d'usuaris

```
Obrim una consola de Windows:
```
```
C:\Windows\System32\cmd.exe
```
```
Usuaris de NetBIOS:
```
```
nbtstat -n
```
```
Usuaris de recursos compartits:
```
```
net USERS
```
```
Usuaris locals i remots:
```
```
[ruta]/SysinternalsSuite/PsLoggedon.exe
```
```
SID de usuarios:
```
```
[ruta]/SysinternalsSuite /PsGetsid.exe
```

## 4

## Anàlisis de serveis

```
Obrim una consola de Windows:
```
```
C:\Windows\System32\cmd.exe
```
```
Serveis en execució:
```
```
[ruta]/SysinternalsSuite /PsService.exe
```
```
Processos actius:
```
```
[ruta]/SysinternalsSuite /PsList.exe
```
```
Events del sistema:
```
```
[ruta]/SysinternalsSuite /PsLoglist.exe
```
```
Obrim Wordpad: Inicio > Wordpad: Executem psList.exe per comprobar el procés.
```
## 5

## Análisis de memoria

· Windows

```
Descarrega l'última versió de ftk imager, dumpit i volatility, investiga com
obtenir la informació següent:
```
```
Realitza un volcat de la memoria sobre un arxiu(amb dumpit i ftk imager), pots
obrir el teu compte de correu per investigarlo més endavant.
```
```
Anàlisis el volcat amb Volatility. (Per realitzar l'anàlisis ho farem més
comodament en un sistema linux per no haber d'instal·lar python3 a windows)
```
```
1. Comprova la versió de volaitily
2. Obteniu informació de la imatge.
3. Veure llista de processos.
4. Filtreu la llista de processos cercant la paraula clau "chrome"
5. Trobeu tots els identificadors oberts per un procés existent.
6. Cerqueu identificadors de fitxers i filtreu per tipus.
7. Volca un fitxer d'un procés existent a l'adreça virtual.
8. Volca tots els fitxers associats amb un PID existent.
9. Veure programes executats amb l'historial d'opcions d'ordres(cmd).
10. Veure connexions de xarxa actives i programes d'escolta.
11. Aboqueu els hash de contrasenya d'usuari de Windows.
12. Imprimiu el UserAssist del registre de Windows.
13. Llista tots els ruscs del registre de Windows disponibles a la memòria.
14. Imprimeix una clau específica del registre de Windows.
15. Imprimeix una clau, subclaus i valors específics del Registre de Windows.
16. ¿Podries saber els comptes de correu oberts i la seva contrasenya?
```

## 6

## Linux

Ara, busca eines y métodes per realitzar la mateixa operativa amb Linux (Debian o
Ubuntu)


