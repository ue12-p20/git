---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
  formats: md:myst
  notebook_metadata_filter: all,-language_info,-toc,-jupytext.text_representation.jupytext_version,-jupytext.text_representation.format_version
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
notebookname: quiz sur numpy
version: '1.0'
---

<div class="licence">
<span>Licence CC BY-NC-ND</span>
<span>Thierry Parmentelat</span>
</div>

<img src="media/inria-25-alpha.png" />

+++

# quiz

pour vous évaluer sur 

* le cours sur numpy
* le cours sur pandas/matplotlib

+++

## mode d'emploi

```{code-cell} ipython3
from nbautoeval import quiz_help
quiz_help("fr")
```

Pour ce quiz <span style="background-color:red; padding: 5px; margin-top: 5px;">l'heure limite est fixée à 14:10</span>

+++

## le quiz

+++

**évaluez la cellule suivante** pour faire apparaitre le quiz

```{code-cell} ipython3
:hide_input: false
:tags: [raises-exception]

from nbautoeval import run_yaml_quiz
run_yaml_quiz("numpy", "quiz")
```

le quiz se trouve dans la cellule précédente, que vous devez évaluer
****
