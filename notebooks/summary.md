| commande | action |
| ----------: | :-------- |
| `git version` | affiche la version de git |
| `git init` | crée un dépôt |
| ￮￮￮￮￮￮￮￮￮￮￮￮ | ***regarder*** |
| `git log` | liste les commits |
|         | `--all` pas seulement à partir du courant |
|         | `--oneline` plus compact |
|         | `--graph` montre la relation parent |
| `git status` | affiche l'état du dépôt: |
|            | branche courante |
|            | en rouge: changements pas dans l'index |
|            | en vert: changements dans l'index |
|            | fichiers pas dans le dépôt|
| `git diff` | entre les fichiers et l'index |
|          | `--cached` entre l'index et le commit |
| `git ls-files` | liste les fichiers dans le dépôt |
| ￮￮￮￮￮￮￮￮￮￮￮￮ | ***créer des commits*** |
| `git add` | verser un changement dans l'index |
| `git commit` | créer un commit |
| ￮￮￮￮￮￮￮￮￮￮￮￮ | ***les branches*** |
| `git branch` | liste les branches connues |
|  | `git branch newbranch commit` | 
|  | pour créer une nouvelle branche | 
| `git checkout` | `git checkout otherbranch` | 
|              | change de branche, l'index et les fichiers |
|              | sont mis en phase avec la nouvelle branche |
|              | `git checkout -b newbranch <commit>` |
|              | crée une nouvelle branche et y va |
|              | raccourci pour `branch` + `checkout` |
| `git merge`  | `git merge <commit>`  | 
| | fusionne le commit |
