---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
  encoding: '# -*- coding: utf-8 -*-'
  notebook_metadata_filter: all,-language_info,-toc,-jupytext.text_representation.jupytext_version,-jupytext.text_representation.format_version
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
notebookname: 'cours git: devoir'
version: '1.0'
---

# Cours git - devoir

+++

## Introduction

+++

### Prérequis

+++

Chaque élève doit avoir créé un compte sur `https://github.com/`

+++

### Groupes et rôles

+++

L'exercice est à réaliser en groupes **de 3 à 4 élèves** (ça peut être plus, mais pas moins de 3), chaque groupe ayant **un meneur identifié** (groupes constitués par ailleurs). Le meneur est le joueur #1, les autres membres du groupe sont numérotés 2, 3, 4.

+++

###  Rendu

+++

chaque groupe envoie un message sur discourse (un fil sera dédié à ce devoir),
en indiquant l'URL du dépôt construit par le groupe sur github

date limite: <span style="background-color:red; padding:8px;border-radius:8px">dimanche 25 octobre</span>

+++

### Critères

+++

pour l'évaluation de votre travail on tiendra compte entre autres 

* du respect des consignes; par exemple si vous n'utilisez pas le nom de dépôt préconisé, ou un autre fichier de départ, vous partez avec un gros handicap…
* de la propreté du dépôt obtenu; ce qui nous intéresse quand on constuit un dépôt, ce n'est pas seulement d'arriver avec le bon fichier à la fin, mais aussi que l'histoire que retracent les commits soit conforme à ce qui est demandé

+++

## Étape 1  - création du dépôt sur github - (à faire par le meneur)

+++

### Résultat attendu :

+++

* le meneur a créé un dépôt sur github, sous le nom `devoir-git`, c'est-à-dire donc en pratique sous un nom comme `https://github.com/lemeneur/devoir-git`
* ce dépôt contient un seul commit avec un seul fichier `README.md`, dont le contenu est **produit** par la cellule Python suivante (évaluez, et copiez-collez)

```{code-cell} ipython3
# copier les lignes produites par cette cellule
# dans le fichier README.md

# mettez ici le nombre de personnes dans votre groupe

how_many_people = 4

for i in range(1, how_many_people + 1):
    print(f"{i:02d} Nom:")
    print(f"{i:02d} github:")
```

### Indices

+++

Il y a principalement deux stratégies possibles pour cette première étape :

* stratégie #1
  * on crée un dépôt local avec `git init`
  * on le remplit (on y crée un commit)
  * on crée un **dépôt vide** sur github (c'est-à-dire sans le `README`)
  * et on pousse le dépôt local sur github;

* stratégie #2
  * on commence par créer le dépôt sur github avec le `README.md`
  * et ensuite on peut le cloner localement

+++

## Étape 2 - droits d'accès - (toujours à faire par le meneur)

+++

Dans cette étape le meneur donne les droits en écriture aux membres de son groupe.

+++

### Indice

+++

Depuis la page projet, allez dans l'onglet `Settings`, puis `Manage Access`.

+++

## Étape 3 - clonage chez tout le monde

+++

Ceux qui n'ont pas ce dépôt sur leur ordinateur personnel le clônent depuis github.

+++

### Indice

+++

Le bouton vert `Code` dans la page du projet sur github.

+++

## Étape 4 - modification locale du *NOM*

+++

Chacun édite le fichier `README.md` pour **remplir son NOM** dans la ligne correspondant à son numéro dans le groupe.
Chacun crée localement un commit avec ce changement dans le fichier.

Assurez-vous que le commit contient bien votre nom (dans la rubrique `Author` de `git log`) pour que l'on puisse vous accorder les points lors de l'évaluation.

+++

### Indice

+++

Pour utiliser correctement votre nom et votre email lors de création des commits, regardez du côté de 

* `git config --global user.name` et
* `git config --global user.email`.

+++

## Étape 5 - tout le monde pousse

+++

Chacun pousse son commit dans le dépôt sur github; dans cette étape, arrangez-vous pour que ce soit **le meneur qui pousse son commit en premier**.

+++

### Indice

+++

Si vous avez des soucis pour pousser votre commit, revoyez dans le cours [le notebook sur le push](https://nbhosting.inria.fr/auditor/notebook/ue12-git:git/notebooks/2-02-synchro-push).

+++

## Étape 6 - tout le monde tire

+++

Chacun tire depuis github; vous devez tous vous retrouver avec les lignes *Nom* renseignées.

+++

## Étape 7 - chacun renseigne son id github

Comme à l'étape 4, mais cette fois vous renseignez votre pseudo github dans la ligne correspondant à votre numéro.

Et vous créez un commit, comme à l'étape 4.

+++

## Étape 8 - chacun pousse

+++

Comme à l'étape 5, sauf que cette fois ce **n'est pas le meneur qui pousse en premier**.

+++

### Indice

+++

Le même qu'à l'étape 5

+++

## Étape 9 - le groupe publie son dépôt

+++

Un des membres du groupe [publie sur discourse, dans ce fil](https://discourse.mines-paristech.fr/t/fil-pour-publier-vos-urls-pour-le-devoir-sur-git/764), l'URL du dépôt github pour évaluation.
