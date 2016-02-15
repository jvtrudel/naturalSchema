# Goals

## Pragmatic goals

   - Fast implementation of ontologies
   - datalysation:
      - fast and easy data input
      - add semantic at input time

## Design Goals



### Souhaitables

Devrait être réaliser si possible

  1. Can use external schema (compatible with exiting techno)
  - Format agnostic (yml, json, xml, ...)


## Expected behavior and usage design


### Terminal ontology

  - classes terminales, qui ne peuvent pas se décomposer en d'autres classes
  - Sont définie par:
    1. une description ou une définition
    2. un ensemble de propriétés qu'ils confèrent à leurs parents.
		- format (regex, specified format)

```
  name: {
		description: "Appellation de cette chose."
		property: nameable
		}
```

Thus if a person is defined as:
```
	person:= (name, birthDate, gender)
```
A person can be named.

### Non-terminal ontology

  - New concept are defined by combining terminal attributes.

```
  person:= (name, birthDate, gender)
	contact:= (phone | email | adress | fax)
	person:= (person,contact)
```

### Core ontologies

  - A convenient small set of concepts that can be used in most cases in a given context.
  - Terminal and non-terminal ontologies can be deduced from a core ontology.

```
core-social ontology

person:= (name, birthDate, gender)
adress:= [doorNumber, street, postalCode, city, region, Contry]
contact:= (phone | email | adress | fax)
organization:= (university|company)
```


### Mécanismes d'extention de sens

#### Ajout d'attribut

  - On peut ajouter un  ou plusierus nouveaux attributs
	- les attribut doit être sémantiquement défini
  - les attribut confèrent à la classe parente des propriétés nouvelles

  - ajout de propriétés


	```
	person.name:Jacque   \\ cette personne peut être nommé
	Jaqcue.age:33    \\  
	```

### Mécanismes de singulariation

  - une objet est abstrait tant qu'il n'est pas singularisé.


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

# grammar



# Benchmarking

## schema.org

http://schema.org/

## foaf (facebook)

http://www.foaf-project.org/

## open graph (facebook)

http://ogp.me/

## Dublin Core

http://dublincore.org/schemas
