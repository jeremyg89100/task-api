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

### Pourquoi tester sur plusieurs versions de Python ?
Si jamais plus tard on veut faire un changement de version de python cela permet de voir déjà les erreurs potentielles et les corriger en amont.

### Que gagne-t-on avec le cache ?
Le cache permet de gagner du temps. Cela va chercher les informations présentes dans le cache à la place d'avoir à les télécharger à chaque fois. 

### Un artefact, c'est quoi ?
Un artefact est un fichier où l'on peut récupérer les informations de l'éxecution d'un job.

### Pourquoi interdire de pousser directement sur main ?
Interdir de pousser sur le main permet d'éviter qu'une personne non autorisée pousse du code. Il s'agit d'une protection supplémentaire.

### Pourquoi Git ne peut-il pas résoudre ce conflit seul ?
Git ne connait pas l'intention des développeurs qui sont à l'origine du conflit. Il faut donc que les développeurs résolvent le problème eux-même pour effectuer la PR.

### Qu'est-ce qui a vérifié le code après la résolution ?
La CI vérifie après la résolution.

### Pourquoi GitHub masque-t-il le secret ?
Github masque le secret pour que personne extérieure puisse avoir accès au code.

### Que se passe-t-il si on le commite dans le dépôt ?
Si on le commit sur le dépôt il faut ensuite le révoquer car tout le monde pourra avoir accès à notre secret étant donné que GitHub dispose d'un historique qui ne peut être supprimé.

###  Secret ou variable : comment choisir ?
Si l'on veut protéger la valeur, il faut choisir secret. Si elle n'a pas besoin d'être protégé alors on peut choisir une variable. 

### Questions : Pour chaque pipeline : quel était le bug, comment l'avez-vous trouvé, comment l'éviter à l'avenir ?
Pour la pipeline A le problème était à la ligne 12, elle n'était pas aligné
Pour la pipeline B il manquait le actions/checkout@v6
Pour la pipeline C il manquait les guillemets pour les versions de pythons à la ligne 9
