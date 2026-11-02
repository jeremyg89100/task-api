# Questions

## TP1 Questions

### Quel test a échoué ? À quelle ligne ? Qu'est-ce qui a permis de le trouver rapidement ?
Il s'agit de is_valid_title qui a échoué. On peut voir que l'erreur a été provoqué dans le test_logic.py à la ligne 13. Cela va renvoyer à la fonction is_valid_title qui a échoué. D'après le commentaire de la fonction on voit que le titre n'est pas valide car la longueur du titre dépasse max_title_length.

### Pourquoi attend-on que la CI soit verte avant de fusionner ?
On attend que la CI soit verte pour confirmer que tous les tests ont bien été effectué avec succès.
