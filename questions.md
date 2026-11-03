# Questions

## TP1 Questions

### Quel test a échoué ? À quelle ligne ? Qu'est-ce qui a permis de le trouver rapidement ?
Il s'agit de is_valid_title qui a échoué. On peut voir que l'erreur a été provoqué dans le test_logic.py à la ligne 13. Cela va renvoyer à la fonction is_valid_title qui a échoué. D'après le commentaire de la fonction on voit que le titre n'est pas valide car la longueur du titre dépasse max_title_length.

### Pourquoi attend-on que la CI soit verte avant de fusionner ?
On attend que la CI soit verte pour confirmer que tous les tests ont bien été effectué avec succès.

## TP2 Questions

### Quelle différence entre un linter (flake8) et un formateur (black) ?
Flake8 s'occupe de vérifier si il y a des imports non utilisés ou de même pour les variables.
Tandis que black est un formateur, il vérifie si les fichiers sont formatés selon la convention.


### Pourquoi séparer lint et test en deux jobs ?
Lint et test sont séparés en 2 jobs afin de pouvoir les tester séparément et éviter de donner trop de responsabilité dans un seul.
Cela permet également de lire les erreurs plus facilement. 
