# TP - Création d'un routeur

## Objectif

L'objectif de ce TP est de voir comment créer "de zéro" une machine sous Debian agissant comme un routeur.

## 1. Création des VMs et installation

Pour ce TP, vous aurez besoin de créer deux VMs :

- Une VM "Client"
    - Debian 12
    - Sans environnement de bureau
    - Une seule interface réseau, connectée à un nouveau segment LAN (que vous appellerez comme vous voulez).
- Une VM "Routeur"
    - Debian 12
    - Sans environnement de bureau
    - Deux interfaces :
        1. La première, connectée au segment LAN créé précédemment
        2. La seconde, en NAT ou en Bridged, et donc connecté à internet

Une fois les VMs créées, et les systèmes installés, éteignez-les et faites des snapshot.

## 2. Configuration réseau statique

Modifiez la configuration réseau de vos deux VMs pour leur assigner une configuration IPv4 statique.

**Attention** : pour le routeur, ne modifiez que l'interface pointant vers le segment LAN, laissez bien l'interface en NAT ou Bridged en configuration automatique.

Le réseau de votre segment LAN sera `192.168.0.0/16`.

La machine cliente aura l'IP `192.168.0.1`.

Le routeur aura l'IP `192.168.255.254`.

**Vérification** : pour vérifier que cette étape fonctionne, assurez-vous que les deux machines peuvent se pinger.

Une fois la vérification faites, éteignez vos VMs et faites des snapshots.

## 3. Routage

Dernière étape : faites en sorte que la machine "Routeur" agisse... comme un routeur !

Cela va vous demander de passer par deux étapes :

1. **Activer l'IP Forwarding**, c'est à dire la possibilité pour le système de réenvoyer des paquets IP qu'il reçoit. C'est facile et rapide à mettre en place.
2. **Activer le NAT**. Pour ça, il va falloir se pencher du côté de NFTables, et de sa commande `nft`. C'est un pare-feu intégré par défaut sur tous les systèmes Debian 12.

**Vérification** : pour vérifier que tout marche, vous devriez pouvoir réussir à ping votre machine hôte depuis la machine "Client". Essayez également de ping "8.8.8.8" !