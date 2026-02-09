# Phishing, ou comment se faire arnaquer en ligne
L'objectif de cette démonstration est de montrer à quel point il est facile de se faire avoir par un phishing de nos jours. L'idée est de montrer la facilité, même pour un profil non technique, de reproduire à l'identique un site internet, et de récupérer les informations transmises. 

## Outils nécessaires
Pour mener à bien cette démonstration, il faudra : 
- un environnement Linux (ici, ParrotOs)
- un outil de copie de site web. Deux outils possibles : 
    - [Social Engineering Toolkit](https://github.com/trustedsec/social-engineer-toolkit) : Outil très (trop) complet, permettant, entre autre, de copier automatiquement un site internet.
    - [Zphister](https://github.com/htr-tech/zphisher) : Outil plus simple, qui ne permet que la copie d'un site à partir d'une liste (trop) réduite de sites possibles.
- Un site "victime" à copier (**sous réserve d'autorisation**)

## Choix de l'outil de copie
Les deux logiciels sont possibles. Cependant, j'ai fait le choix de Social Engineering Toolkit, plus complet, car il permet de copier pratiquement n'importe quel site en fournissant l'URL. Zphister ne propose qu'une liste prédéfinie de sites (Google, Netflix, Paypal, etc...). **Avec l'accord préalable du responsable de la structure d'accueil**, il est ainsi possible de copie le site de la structure, pour rendre plus personnel et impactant la démonstration. Il est alors important d'expliquer que la copie ne se fait qu'en local, qu'elle n'est pas mise en ligne, et qu'elle sera supprimée devant témoins à la fin de la démonstration. Si la structure d'accueil ne possède pas de site avec espace personnel et page de connexion, ou bien si refus, Zphister est alors le plus simple. 

## Mise en oeuvre avec Social Engineering Toolkit
1. Lancer l'outil dans le terminal en `sudo` avec ```sudo setoolkit```
2. Choisir la séquence suivante pour atteindre le bon mode, en rentrant les numéros correspondants : Social-Engineering Attacks -> Website Attack Vectors -> Credential Harvester Attack Method -> Site Cloner
3. Choisir l'exploitation en local en laissant la valeur par défaut à l'étape 3
4. Entrer l'URL à cloner. Pour l'exemple, nous prendrons https://github.com/login
5. Dans un navigateur web, se rendre sur `localhost` ou `127.0.0.1` et constater la copie exacte du site.
6. Si possible, garder le terminal et le navigateur cote-à-cote.
7. Rentrer des informations de connexion (**fictives bien sûr**)
8. Constater que le terminal affiche les informations entrées, et que nous sommes redirigés vers le site légitime, maintenant que le mal est fait.

## Mise en oeuvre avec Zphister 
1. Lancer l'outil dans le terminal avec `./zphister.sh`
2. Choisir la cible avec le numéro correspondant parmis la liste des sites proposés.
3. Choisir la destination. Préferer le `localhost` avec 01, puis un port (par défaut, ou un port libre, selon préférence personnelle)
4. Le site est dispo sur le `localhost` au port choisi (par défaut `8080`) 

> Certains sites peuvent ne pas charger le css, je ne sais pas comment fix cela. De plus, certains réseaux d'entreprises peuvent bloquer les requêtes lancées par l'outil, donc préferer une connexion personnelle type 5G.

5. De la même manière que l'autre outil, les informations de login entrées par la victime sont relevées dans le terminal. Le faux site redirige vers le site légitime immédiatement.

## Détails techniques
Si on veut recommencer la démonstrations avec un autre site, il faudra complètement quitter l'outil, voire ouvrir un nouveau terminal pour être sûr. Il arrive que le localhost ne se mette pas à jour.

## Vidéos
- ![Démo Social-Engineering Toolkit](video/demo_SET.mp4)
- ![Démo Zphister](video/demo_zphister.mp4)