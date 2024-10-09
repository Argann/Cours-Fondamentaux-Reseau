# TP - Couches OSI et analyse de paquets

## Objectifs

Le but de ce TP est de comprendre le fonctionnement des couches OSI, et de voir comment elles s'appliquent "dans la vraie vie".

## 1. Théorie

Sur papier, décrivez le rôle de chaque couche OSI en une phrase simple.

Utilisez vos propres mots, ne faites pas juste un copier-coller du cours ou d'internet !

Même si certaines couches vous semblent peut-être obscures, essayez de jouer le jeu au maximum.

Une fois terminé, mettez-vous en binôme, et essayez d'expliquer à votre camarade ce que vous avez pu comprendre.

Si vous n'êtes pas d'accord sur certains points, essayez de comprendre pourquoi !

## 2. Pratique : analyse de paquets

En utilisant **Wireshark**, analysez un paquet contenant une requête HTTP.

- Vous pouvez filtrer les paquets affichés avec la barre en haut de l'écran
- Émettre une requête HTTP est très simple : chargez simplement une page web avec n'importe quel navigateur !

Une fois trouvé un paquet intéressant, répondez aux questions suivantes à l'écrit :

1. Quelles couches OSI sont facilement identifiables dans la structure du paquet ?
2. Voyez-vous une adresse MAC ? Si oui, laquelle ?
3. Voyez-vous une (ou plusieurs) adresses IP ? Si oui, lesquelles ?
4. Quel protocole de couche 4 à été utilisé ? Quels ports utilise-t-il ?

Pour terminer, décrivez en quelques phrases comment le processus d'encapsulation et de désencapsulation a eu lieu, en prenant ce paquet comme exemple.