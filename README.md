# Problemes
https://github.com/keon/algorithms

# Sessió 1. Python 1: tipus, llistes i iteracions

## Objectius
+ Saber fer operacions i gestionar variables amb enters, booleans, decimals i cadenes de text
+ Saber fer operacions bàsiques amb llistes
+ Conèixer el codi dels blocs ``if`` i de les iteracions ``for``

## Tipus 

Hi ha alguns tipus de dades bàsics que heu de conèixer per poder treballar amb Python: les cadenes de text, els enters, els decimals i els booleans.

### Cadenes de text (strings)

Una string és un text amb 0 o més caràcters. A Python els strings s'indiquen amb cometes simples o dobles. Si cal posar cometes dins el text podem usar la barra inversa \

```python
print('Això m\'agrada')
```
També hi ha una altra solució:

```python
print("Això m'agrada")
```

### Enters (integers)
Un ``int`` és un nombre que pertany al conjunt format pels nombres naturals, els negatius dels nombres natuarals i el 0. Els ordinadors poden respresentar enters fins a un límit (sempre ho farem amb un conjunt finit de bits) però amb els ordinadors actuals i per la majoria de problemes això no representa una limitació. 

Executa aquest codi i mira el resultat:

```python
print(234**7456)
```

Els enters s'han d'escriure sense el punt dels milers. Prova el següent codi i observa què passa:

```python
print(1.000.000.000)
```

Els enters també es poden representar en binari usant la funció ``bin``:

```python
print(4)
print(bin(4))
```

### Decimals (floats)
Un ``float`` és un nombre decimal. A Python, com en anglès, s'escriuen amb un punt separant la part entera de la part decimal. Com en el cas dels enters també hi ha un límit en la seva representació i en la precisió; aquests límits ens afectaran si usem càlculs amb nombres molt grans o amb molta precisió.

Degut a la representació interna dels decimals a Python, algunes operacions poden retornar valors curiosos. Per exemple:

```python
print((431/100)*100)
```

Retornarà 430.99999999999994 i no 431 com seria d’esperar. Per evitar-ho podeu usar les funcions ``round()``, ``ceiling()`` i ``floor()`` que arrodoneixen a l’enter més proper, a l’enter superior o a l’enter inferior respectivament.

```python
a=4.7
b=5.3
import math
print (a, round(a), math.ceil(a), math.floor(a))
print(b, round(b), math.ceil(b), math.floor(b))
```
### Booleans

Per conèixer més en detall els booleans consulteu si-us-plau els apunts de l'assignatura sobre llistes

- [Booleans](apunts/booleans.ipynb) 

### Conversió forçosa de tipus

A vegades podem forçar que una dada passi a ser d'un tipus determinat. Per fer-ho usarem l'expressió: ``nomTipus(valor)``. Vegeu els següents exemples:

```python
print(15/4)
print(int(15/4))
print(15+4)
print(float(15+4))
print("Jo tinc "+str(10)+" pomes")
```


## Llistes 

Per conèixer més en detall les llistes consulteu si-us-plau els apunts de l'assignatura sobre llistes

- [Llistes](apunts/colleccions.ipynb) 


## Blocs de control 

Per conèixer més en detall el funcionament de les estructures de control consulteu si-us-plau els apunts de l'assignatura sobre llistes

- [Estructures de control](apunts/control.ipynb)

# Sessió 2. Python 2: Estil programació, descomposició en funcions i estructures de control

## Objectius
+ Aprendre bones pràctiques en la denominació de funcions i variables i d'ús dels comentaris
+ Saber descomposar funcions en blocs reutilitzables
+ Conèixer el codi de les iteracions ``for`` i ``while``

## Estil de programació

Els programes sovint es comparteixen entre diferents programadors o es modifiquen al cap d'un temps.

Per això és important que estiguin escrits de forma clara i seguint unes convencions d'estil per fer-los més llegibles.

Cada llenguatge sol tenir unes directrius d'estil. A Python s'usen les directrius [PEP8](https://www.python.org/dev/peps/pep-0008/)

Spyder ens ajuda a seguir aquestes directrius si configurem l'editor per a què ens avisi. Això es fa amb ``Herramientas - Preferencias - Editor - Análisis de estilo del código en el Editor``.

Amb això Spyder ja ens avisarà si no seguim les convencions bàsiques de PEP8.

### Comentaris

Inicieu les funcions amb unes línies de comentaris delimitades per `"""` que indiquin l'objectiu de la funció. Incloeu una línia de comentari pels paràmetres, i una línia pel què retorna.

Incloeu comentaris breus addicionals entre línies amb # per explicar algun detall del codi en particular que no quedi prou clar.

```python
# Exemple

def primerDarrer8(llista):
    """
    Aquesta funció, donada una llista d’enters,
    retorna True si 8 és el primer o el darrer element de la llista,
    retorna False altrament
    :param llista una llista d'enters
    :return: True si 8 és a l'inici o final, False altrament
    """
    if llista[0]==8 or llista[-1]==8: # Amb -1 comencem pel darrera
        return True
    else:
        return False
```		


### Noms de funcions i de variables
Useu noms en minúscules per les funcions i variables. Si són compostes per dues o més paraules, inicieu la segona i següents amb majúscules.

```python
a = 5
meuCotxe = "Toyota"
valorAproximat = 3.567
def calculSuma(a,b):
    pass
```
Ara bé, per a les (falses) constants useu majúscules:

```python
MAXIM = 9999999
```

### Identació
Useu 4 espais per marcar els diferents nivells de blocs.

Si el codi d'una funció ocupa dues línies, identeu-lo per a què siguin consistents.
```python
def funcio():
    print("les instruccions comencen 4 espais a la dreta")
    for i in range(2):
        print("per cada nou bloc, 4 espais més")
		print("pero si vull posar moltes coses en un print",
              "i no m'hi caben, idento per a què sigui",
              "consistent")
```

### Llargada de les línies
Una línia de codi ha d'ocupar com a màxim 79 caràcters.
Si una línia no hi cap en 79 caràcters, la puc continuar amb el caràcter \

```python
with open('/path/to/some/file/you/want/to/read') as file_1, \
     open('/path/to/some/file/being/written', 'w') as file_2:
    pass
```
 El caràcter \ no cal si la continuació és dintre el mateix parèntesi que la línia anterior

```python
print('a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r',
      's', 't', 'u', 'v', 'x', 'y', 'z')
```

### Línies en blanc
Les funcions han d'anar precedides i seguides de dues línies en blanc.

### Espais en blanc
Deixeu espais en blanc davant i darrera dels operadors. Deixeu un espai en blanc darrera de la coma. No poseu espais en blanc al final de les línies de codi. Acabeu sempre les funcions amb un salt de línia.

```python
a = b + c
llista = ['a', 'b', 'c']
```

### Import
Posar cada import en una línia diferent. Situar-los al principi de tot.

```python
import math
import string


def funcio():
    pass
```

## Descomposició en funcions

En cursos més avançats realitzareu funcions força complexes que consistiran en molts passos. I en l'entorn laboral sovint aquestes funcions complexes repeteixen codi ja fet.

Per tal de facilitar la reutilització del codi, i facilitar el manteniment i llegibilitat, es recomana descomposar les funcions en parts petites amb significat.

Quan us enfronteu amb un problema, heu de mirar d'identificar aquelles parts del codi que resolen un problema i separar-les del codi principal.
Finalment, hi haurà una funció principal, que anirà cridant aquestes funcions més petites de forma ordenada, per resoldre el problema gran.

## Iteracions: `for` i `while`

Per conèixer més en detall el funcionament de les estructures de control, consulteu si-us-plau els apunts de l'assignatura sobre estructures de control:

-  [Estructures de control](apunts/control.ipynb)

## Codificació de caràcters

Per saber com es representen els caràcters a l'ordinador, consulteu si-us-plau els apunts de l'assignatura sobre codificació de caràcters:

-  [Caràcters](apunts/caracters.ipynb)


