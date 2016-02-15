# Description

# Objectifs du schéma

  - construction rapide d'ontologie
  - datalysation:
    - entrer rapide des données
    - ajout de sémantique
  - utiliser pour stocker des informations
  - utiliser pour injecter du contenu dans pages web
  - supplanter l'usage de word
  - multilingue

## Critères concrèts

# Design

## Natural Schema

  - Natural Schema (ne semble pas exister dans l'univers de la prog)
  - ns (format obscur et obsolète selon [file extensions](http://www.file-extensions.org/ns-file-extension))


## Design Goals



### Vision

Impossible d'apporter des modificaitons qui ne répondes pas à ces critères.

  1. Semantique
  - Le plus près possible du language naturel
  - Extension minimale des classe: Évite de polluer la sémantique avec plein d'attributs
  - Génération de sens par composition et particularisation (du général au particulier)
  - Uitlisation extensive de listes (pluriel)
  - Référencement par id (réalisation vs abstraction)





### Souhaitables

Devrait être réaliser si possible

  1. Can use external schema (compatible with exiting techno)
  - Format agnostic (yml, json, xml, ...)


## Implementation strategies

### Mécanisme de création d'objet composé

  - Utilise les classes de bases

  - utilise une syntaxe par chainage

````
table
  .materiel.bois
  .longueur.cm.18
````


### Mécanisme de chainage

possibilité d'utiliser une syntaxe du genre:

```
table
  .materiel.bois
  .longueur.cm.18

table.materiel.bois.longueur.cm.18
```




### Mécanisme de composition (atomic design)

 - Schema atomic
 - Schema composé

  - Composition par ajout d'attributs
  - Composition par définition du format
  - composition par définition d'unité (eg. longueur.cm, longueur.m)

### Étendu minimales des classes auxquelles on ajoute des propriétés


Example:
```
personne: {name, birthDate}
personne.contact: {phone,email,adress, fax ...  }
```

### Namespacing

 - utilisation de namespaces



### Composed vocabulary synthax (???)

  - possibilité de combiner des mots clefs
  - avantages: extreme-markdown-style, proche du laguage naturel

```
phone.formatCanada: "1-418-204-5436"
```

### Mécanisme de gestion des formats de données entrantes

```
phone.formats:{canada, france, includeInternationalCode, includeRegionalCode, include}
```



## Difficultés

  - doit écrire une grammaire...



# Benchmarking

## schema.org

http://schema.org/

## foaf (facebook)

http://www.foaf-project.org/

## open graph (facebook)

http://ogp.me/

## Dublin Core

http://dublincore.org/schemas
