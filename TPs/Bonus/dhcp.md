# TP - Mise en place d'un serveur DHCP

## Objectif

L'objectif de ce TP est de voir comment mettre en place et configurer un serveur DHCP au sein d'un réseau privé.

## 1. Création des VMs et installation

Vous pouvez reprendre les VMs créées pendant le TP "Routeur".

Si vous ne l'avez pas fait, reprenez simplement l'étape 1 de ce TP.

## 2. Mise en place d'un serveur DHCP

Une fois les VMs prêtes, installez et configurez un serveur DHCP sur la machine "Routeur".

Quelques astuces :
- De préférence, utilisez `kea` comme serveur DHCP : c'est le plus récent, et celui qui est préconisé.
- Renommez le fichier de configuration par défaut de `kea` avant de créer le votre : vous pourrez ainsi retourner le consulter en cas de problème !
- Le DHCP n'est à configurer que pour IPv4
- N'oubliez pas de repasser la conf IPv4 de "Client" en automatique !

**Vérification** : redémarrez le service networking sur "Client", et vérifiez que vous récupérez bien une adresse IP dynamiquement !