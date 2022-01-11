# Web des données

## Introduction

Données d'une page html : compliqué à extraire car les données sont perdu au milieu d'une page html énorme. Si on veut écrire un programme pour extraire les données :
- fastidieux 
- Et non réutilisable si la structure de la page html change

pourtant côté serveur les données sont bien organisé dans une base de données.
de plus les page html ne contienne pas que du texte.

**Comment extraire les informations de manière automatique ?**

le langage commun RDF qui permet d'exprimer des information sur des ressources. RDF est simple.

### RDF
- Chaque ressources est identifié par un identificateur
- Expression sous forme de triplet  : Sujet (URI) , prédicat (Relation) , objet (Ressource avec URI ou littéral)
un *URI* est un identificateur unique.

# Notion de base 

## URI et URIref 
> URI :Une chaine de caractère qui identifie une ressource ou un concept. 

 Une URL est une URI, mais une URI n'est par une URL car toutes les ressources ne sont pas disponible sur le web. RDF n'utilise pas des URI mais des URIref (URI references)
> URIref  : Une URIref est une URI acompagnée d'un identificateur de fragment, préfixé par #

Il peut n’y avoir aucun lien particulier entre plusieurs URIref de la même URI.

## XML 
La plupart des langages du web sémantique utilisent une notation XML


# RDF

> RDF est un langage permettant de représenter des formations sur des ressources RDF permet de combiner des élément  en triplets sujet - prédicat  - objet. Un tel triplet est appelé déclaration 

> Un déclaration est formée : 
>  - d'un sujet qui est une URI(ref).
>  - d'un prédicat qui est une URI(ref).
>   - d'un objet qui est une URI(ref) ou un littéral.


## Syntaxe 
### RDF/XML 
 RDF/XML est un format basé sur XML permettant de représenter des déclaration RDF. Mais verbeux et perte la simplicité des triplets
### Notation 3
exemple :
```
Sujet
Prédicat 
Objet .

Sujet1
Prédicat1
Objet1 .
```

### Nœud nuls

Dans certains cas, on veut représenter des données sur un sujet, sans en faire une URI. (Exemple adresse postale). Utilisé assez rarement.

### Littéraux typés

RDF ne contient pas de type mais permet d’associer un type à un littéral. Ce type est identifié par son URI.

Exemple `"literral"^^URI_type`
Simplification :
```
@prefix xsd:<http://www.w3.org/XMLSchema#> .
exmembre:m87 exvoc:age "27"^^xsd:integer```
