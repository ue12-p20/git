---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
  notebook_metadata_filter: all,-language_info,-toc,-jupytext.text_representation.jupytext_version,-jupytext.text_representation.format_version
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
notebookname: bonnes pratiques
version: '1.0'
---

<div class="licence">
<span>Licence CC BY-NC-ND</span>
<div style="display:grid">
    <span>Thierry Parmentelat</span>
    <span>Valérie Roy</span>
</div>
</div>

<img src="media/inria-25-alpha.png" />
<img src="media/ensmp-25-alpha.png" />

+++

# commits & bonnes pratiques

+++

Une notebook très court, où on revient rapidement sur la bonne façon de découper son code en commits, et de rédiger les messages qui vont avec.

+++

## le contenu des commits

+++

### ne pas tout mélanger

La première recommandation, sans doute la plus fondamentale, est de **bien regrouper les modifications qui vont ensemble**. 

En effet il arrive souvent qu'on se retrouve avec dans les fichiers une accumulation de changements; par exemple, pour écrire une nouvelle feature, travail qui a pris deux jours entiers, on a aussi corrigé un typo dans un commentaire, et récrit un bout de code pour utiliser une technique qu'on vient d'apprendre et qui est plus sûre.

À ce stade on va committer, il **faut absolument** tirer profit de l'index, qui on l'a vu nous permet justement de **ne pas tout committer d'un coup**, pour découper ces changements **en 3 commits distincts** - ou plus le cas échéant, si la feature elle-même peut être logiquement découpée en plusieurs étapes.

+++

### pourquoi ?

L'intérêt, c'est que

* imaginez, vous devez reporter la correction d'un bug dans une version client qui est vieille de deux mois;  
  le bug est déjà corrigé dans la version de développement  
  si la correction du bug a été bien proprement isolée dans un commit qui ne fait que ça, on va facilement pouvoir appliquer ce commit sur la branche de maintenance (pour les curieux, voyez `git cherry-pick`)  
  mais si au contraire c'est tout mélangé avec d'autres choses, ça va être problématique et on va devoir réappliquer le bugfix à la main, ballot !

* il est possible aussi de récrire l'historique (en utilisant `git rebase`, qu'on n'aura pas le temps de voir pendant ce cours malheureusement, mais les curieux peuvent s'y intéresser, si c'est votre cas regardez surtout `git rebase --interactive`)  
  avec cet outil on peut entre autres changer l'ordre des commits, et/ou les fusionner (c'est faisable, mais plus compliqué, de découper un commit en morceaux);  

Ceci nous amène naturellement à créer **plusieurs petits pas** plutôt que **un seul gros** - sans non plus tomber dans l'excès inverse, idéalement à la fin quand on sera sûr d'avoir corrigé le bug ce qu'on voudra c'est un seul commit pour la correction du bug.

+++ {"tags": ["level_intermediate"]}

### les jeux de tests

Signalons enfin - on aura l'occasion d'y revenir au second semestre - que dans un vrai dépôt, on va presque systématiquement trouver, en plus du code à proprement parler, les jeux de test qui permettent de s'assurer que le code fonctionne.

De cette façon, au prochain commit, on pourra automatiquement détecter une éventuelle régression, il suffira de relancer les jeux de test; c'est en gros le principe de ce qu'on appelle l'**intégration continue** (ou CI en anglais), qui consiste à s'arranger pour que les tests soient effectués à chaque commit.

+++

## le message des commits

+++

### quoi mettre dans le message

Au début on n'a pas les idées claires sur ce qu'il est intéressant de mentionner dans le message attaché à un commit.

On peut commencer par dire **ce qui n'est pas intéressant** : ce n'est pas la peine de reprendre la liste des fichiers / fonctions / numéros de lignes modifiés, tout ça est calculable et tous les outils d'UI graphique autour de git vous montreront tout ça très bien - en plus ce sera garanti d'être correct.

Il est souvent plus pertinent d'expliquer **pourquoi** on a fait le changement, plutôt que **comment** on l'a fait. 

Dites-nous par exemple que c'est la correction du bug numéro tant et tant; ou que c'est un refactoring qui prépare la feature telle et telle. 

Mais ne nous dites pas que vous avez remplacé la fonction `schmoll` par la classe `Truc`, qui est quelque chose qu'on va voir facilement en lisant les différences..

Avec un peu d'expérience on comprend assez vite ce qu'il est utile de mentionner ou pas; 
clairement le fait de travailler en équipe, et donc d'être en situation de lire la production des autres, aide bien.

+++

### une ligne de synthèse + une ligne blanche + du baratin

Dernier détail, ça varie selon les projets, mais un usage assez répandu consiste à rédiger son message en mettant

* une ligne de synthèse
* une ligne blanche pour bien séparer
* ensuite autant de détails qu'on veut

ça pourrait donner par exemple

```
a synthetic line that summarizes it

the gory details that you believe
are relevant to mention here
for example to motivate the technical choices made
(which could also be written in comments in the code
 if that deserves to be made permanent)
```

ce qui permet alors à - notamment - `git log --oneline` de présenter un résumé pertinent.

+++ {"tags": ["level_intermediate"]}

### spécifique à github

Lorsqu'on utilise une plateforme comme github, il est fréquent de mentionner dans le message des références à d'autres événements du projet.

On n'en a pas encore parlé, mais dans un projet github il y a la notion de *issue*, qui sont des simples fils de discussion, qui peuvent servir entre autres à signaler un bug

ainsi si par exemple l'*issue* numéro 123 signale un bug, et qu'on commite une correction pour ce bug, on va écrire simplement quelque part `close #123`, ce qui permettra de lier le commit avec l'*issue*, et d'améliorer la traçabilité - et même de fermer automatiquement l'issue en question.

On peut référencer de cette façon toutes sortes d'objets autres que les *issues*, voir les détails ici :
https://docs.github.com/en/github/writing-on-github/autolinked-references-and-urls
