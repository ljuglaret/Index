<!--
- title : partie 2
Créer son type date en elm

- description :
 Le 29 Février 2100 existe t il ?
Nous allons voir comment grace aux types d Elm nous allons garantir la validité d une date à la compilation.
Cet exemple permettra de comprendre l usage des let-exressions et des types algebriques.

- author : Laure Juglaret
- theme : solarized.css
- transition : convex
- slideNumber : true -->  

<style type="text/css">
  .reveal li code { font-size:  100%; width : 600pt; }
</style>


#  partie 2  bibli Date en elm


---
- on peut redéfinir des operations arithmétiques
entre une  date et un nombre de jours :
 - <+> addition
 - <-> soustraction

    Une convention peut etre d appliquer
    les regles habituelles de l arthmetique

    Par exemple : 
    date <+> -3  : revient a date <-> 3
----
- Mais aussi des operations booleennes entre deux dates
    - <=
    - >=
    - ==
    - <
    - >
----
- Étape 1 : Écrire une fonction qui compare deux dates (Order)
- Étape 2 : On définit supOuEgal(>=) et egal(==) grâce a la fonction précédente
- Etape 3 : On déduit les autres: 
    - <  :  non(>=)
    - >  :  non(<) et (non (==))
    - <= :  <  ou ==

---

Affichage
Pour une meilleure visualisation on affiche une date
sous la forme Jour - NºJour  Mois - Annee
```elm
aff : Maybe Date2 -> String 
```
Exp 
```elm
date3 = newDate{jour = 11, mois = Septembre, annee = 2018}
aff date3
``` 

"Mardi - 11 Septembre - 2018" 

