# TP - Routes

## Objectifs

Le but de ce TP est de comprendre le principe de routage IP, pour permettre la communication entre des réseaux distincts.

## Pré-requis

Idéalement, vous devriez terminer le cours Netacad "Premiers pas avec Cisco Packet Tracer" avant de faire ce TP.

## 1. Création de réseau

Le but de cet exercice est de créer, sur Cisco Packet Tracer, trois réseaux différents.

Chaque réseau aura une topologie en étoile ayant plusieurs dispositifs utilisateurs (ordinateurs, laptops, smartphones, etc.), regroupés autour d'un simple switch.

Chaque réseau aura sa propre adresse de réseau, différente des autres, et chaque dispositif utilisateur aura une adresse IPv4 unique dans son réseau. Les adresses IPv4 de ces dispositifs seront à configurer manuellement, sans "DHCP".

Les réseaux ne seront _**pas**_ reliés entre eux !

**Vérification** : Pour valider cette étape, vous devez pouvoir faire en sorte que les dispositifs _d'un même réseau_ puissent se pinger.

Par exemple, si dans un de mes trois réseaux j'ai un PC (192.168.0.1) et un laptop (192.168.0.2), je dois pouvoir ouvrir un "Command prompt" sur le PC, taper la commande `ping 192.168.0.2` doit me donner le message 

`Reply From 192.168.0.2: bytes=32 (...)`

Si un autre message s'affiche, c'est qu'il y a un problème quelque part.

## 2. Relier les réseaux

Maintenant que chaque réseau est fonctionnel, essayons de les relier.

Votre objectif est de relier les trois réseaux (que l'on va appeler A, B et C) de la façon suivante :

`A <-> B <-> C`

Il ne doit _pas_ y avoir de liens direct entre A et C.

Vous devrez donc utiliser deux routeurs : un premier entre A et B, et le second entre B et C.

Chaque routeur aura donc deux adresses IP, une sur chaque réseau sur lequel il est connecté.

Attention à ne pas donner deux fois la même adresse IP dans un réseau !

Ne configurez pas encore de routes, faites juste les branchements et les configurations IP statiques.

**Vérification** : Vous devriez pouvoir ping vos routeurs (au sein d'un réseau)... mais c'est tout.

## 3. Routes !

Configurez les routeurs pour qu'ils puissent router les paquets entre les deux réseaux sur lesquels ils sont directement connectés.

Ensuite, configurez la passerelle par défaut de chaque routeur pour être l'autre routeur. (La passerelle par défaut du routeur A-B sera le routeur B-C, et la passerelle par défaut du routeur B-C sera le routeur A-B).

Enfin, configurez les routes de chaque dispositifs utilisateurs (définir une passerelle par défaut devrait suffire, mais réfléchissez bien !).

**Vérification** : Normalement, n'importe quel dispositif utilisateur doit pouvoir communiquer avec n'importe quel autre dispositif ! Depuis un poste du réseau A, tentez de `ping` un poste du réseau C !