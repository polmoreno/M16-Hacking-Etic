## UF1: File Carving

Eines a utilitzar

```
● xxd
● tr
● grep
● dd
● echo
● bc
● cut
```

## 1

## Introducció

En aquesta pràctica escanjearem una imatge de disc, per obtenir un fitxer png que hi
es contingut a dintre.

En la imatge de disc es troba una imatge en format png i volem recuperar-la.


## 2

## Preparació

### Descarrega la següent imatge

[imatge](..RAWs/imagen)

### Busca on comença el fitxer dintre de la imatge

[Què es el _magic number_?](https://ca.lmgtfy.app/#gsc.tab=0&gsc.q=magic%20number%20hard%20drive)

Per què aquest número tan raro?

Llavors, ¿hi ha un [magic number](https://asecuritysite.com/forensics/magic) per cada tipus d'arxiu? [Resposta](https://www.incibe-cert.es/blog/file-carving)

```
xxd imagen | sed 's/ //g' | grep 89504e
```
```
● La primera columna ens indica la posició dels bytes dins el fitxer  
● L'última el codi ascii  
● Les intermitjes, el valor hexadecimal  
```
`
Tenint en compte que la primera columna de xxd ens mostra la posició dins del fitxer
haurem de guardar el número i convertir-lo a decimal

```
echo "ibase=16;00809C00" | bc
```
ara sabem on comença el fitxer, i haurem de saber on acaba, sabem que el final d'un
png està indicat amb 49454e44ae

### Busca on acaba el fitxer

en aquest exemple tant inici com final els trobem a la mateixa línia però podria ser
que no fos així

```
echo "ibase=16;0080A300" | bc
```
xxd ens mostra(per defecte) 16 bytes per línia i haurem de comptar els números fins al
final del magic numer i dividir entre dos per sumar-lo a la primera columna.

Ens surt 11 que en hexadecimal es B

```
xxd imagen | sed 's/ //g' | grep 49454e4ae
echo "ibase=16;0080A300+B" | bc
```
### Busca el tamany del fitxer

Un cop tenim l'inici i el final haurem de fer la resta per saber el nombre de bytes
que ocupa la imatge per indicar-ho en el dd

```
echo "8430347-8428544" | bc
```
### Exporta el fitxer al resultat

Utilitzant dd retalla els bytes corresponents a la imatge png i guardar-la com a
resultat.png.

```
dd if =imagen of=result.png skip=8428544 bs=1 count=
```
## 3

## Exercici

```
● Fes un script que automatitzi la recuperació de aquesta imatge
● Ara, fes un script en python
● Fes un script que busqui els fitxers que hi han i hi han hagut al teu disc dur
de tipus .gz, i obtinguis com a resultat un llistat (Encara que els fitxers
estiguin malmesos)
```

