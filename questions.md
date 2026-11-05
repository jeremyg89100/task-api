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


## TP3 Questions

### Taille
48.9MB

### Difference entre une image et un conteneur ?
L'image est le guide qui permet d'obtenir le conteneur. 
Le conteneur est donc l'instance de l'image. 

### A quoi sert le .dockerignore
Le dockerignore permet d'empêcher de push certains fichiers qui doivent rester privé (exemple: .env)

###  Que gagne-t-on à décrire le lancement dans un fichier plutôt que dans une longue commande ?
Cela permet de gagner en lisibilité

### Pourquoi build attend-il test ?
Build attend test pour ne pas créer une conteneur avec un code qui ne fonctionne pas

### Pourquoi éviter le tag latest en production ?
Il faut éviter le tag latest car le tag change tout le temps alors que le principe du conteneur est qu'il doit être immuable.

### À quoi sert un test de fumée ?
Le test de fumée sert à vérifier que l'app fonctionne

### Pourquoi demander une approbation humaine avant la production ?
Afin de rajouter une sécurité et d'avoir une vérification humaine avant de partir en production.

### Pourquoi ne pas exécuter une application en root dans un conteneur ?
On ne veut pas donner trop de droits aux utilisateurs et provoquer une faille de sécurité

## Questions TP4

### Avec vos mots : c'est quoi un pod ? Un deployment ? Pourquoi un `namespace` ?
Un pod est un conteneur de kubernetes.
Le deployment est le nombre de pod que l'on souhaite. Peu importe si il y a un pod qui tombe, un autre sera crée pour toujours respecter ce nombre.
Un namespace est le nom du dossier où se trouve le cluster.

### *Observation TP4-6 (réponse écrite, pas de capture) :** à un moment, avez-vous vu les **5 pods** ? Pendant combien de temps environ ? Que s'est-il passé ensuite ?
Les pods se sont ajoutés en pending puis sont devenus des ImagePullBackOff

### Que signifie `selfHeal` ? Pourquoi le retour arrière est-il simple en GitOps ?
selfHeal signifie que kubernetes va se mettre à jour en fonction du github automatiquement. Le retour en arrière est GitOps car il y a une trace du commit qui a effectuer le revert.
