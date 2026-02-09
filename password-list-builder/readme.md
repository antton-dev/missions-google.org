# Construction d'une wordlist de mots de passe pour une personne spécifique
La plupart des personnes construisent des mots de passe qui répondent à un schéma connu et ultra commun : `prenom` `Année de naissance` `caractère spécial`.
Nous pouvons donc construire une liste de mots de passe potentiels à partir de certaines informations, dans le but de brutforcer un accès à un compte.

## Outils nécessaires
- Un environnement linux
- Cupp
- Le portrait d'une **personne volontaire** ou d'une **personne fictive** (ou soi-même)

## Mise en oeuvre
1. Lancer l'outil dans un terminal linux en mode interactif avec `cupp -i`
2. Répondre aux différentes questions. Pour chaque question, il est possible de ne pas remplir si on ne connait pas l'information.
3. La wordlist est stockée dans le répertoire courant sous la forme `prenom.txt` où prénom est le prénom de la victime.

## Vidéo
![Vidéo de démonstration](video/demo.mp4)