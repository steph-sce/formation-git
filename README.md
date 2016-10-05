# Différents cas de mauvaise utilisation de git

Ce dépôt contient un travail dont le master est en V1, en production : un carré jaune sur fond jaune, qui s'anime verticalement a^rès un clic sur un bouton. La V2 souhaitée est un carré rouge sur fond jaune qui doit se déplacer du coin supérieur gauche au coin inférieur droit. Un sprint est prévu afin de réaliser cette fonctionnalité.

Voici différentes configurations de collaboration qui mènent à des diffcultés :

## 1 - le manque de modularité

 - Collaborateur 1 : crée une branche de dev, la checkout et la push
 - Collaborateur 2 : pull la branche dev et checkout
 - Collaborateur 1 : code la CSS, effectue un commit sur la branche de dev et push
 - Collaborateur 2 : code la fonction et réindente, effectue un commit et pull pour pouvoir pusher

> Conflit : la réindentation a eu un effet de bord sur la CSS, une séparation en différents fichiers est souhaitée

## 2 - le manque d'ordonancement

 - Collaborateur 1 : crée une branche de dev, la checkout et la push
 - Collaborateur 2 : pull la branche dev et checkout
 - Collaborateur 1 : code la CSS, effectue un commit sur la branche de dev et push
 - Collaborateur 2 : s'aperçoit du problème de modularité et sépare les fichiers, commit et pull

> Conflit : le spit est effectué trop tard, une analyse technique en amont est souhaitable à l'écriture du backlog

## 3 - un isolement trop important

 - Collaborateur 1 : crée une branche de dev, la checkout et la push
 - Collaborateur 2 : pull la branche dev et checkout
 - Collaborateur 1 : sépare les fichiers et push
 - Collaborateur 2 : code la fonction et indente, puis commit
 - Collaborateur 1 : code la CSS et commit
 - Collaborateur 1 : refactorise le javascript et commit et push
 - Collaborateur 2 : pull pour pusher avant les tests et la mise en prod
 
 > Conflit : il aurait suffit que les deux collaborateurs push et pull régulièrement pour n'avoir aucun problème et continuer de coder sur la version de l'autre
 
 
 

