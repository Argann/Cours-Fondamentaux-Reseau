## 1. Binaire

- 1100 0000 . 1010 1000 . 0000 0000 . 0000 0001
- 1010 1100 . 0011 1110 . 0000 1110 . 0000 0101
- 0000 1010 . 0000 0000 . 0000 0000 . 1111 1110

- 192.168.1.1
- 172.16.0.2
- 10.0.17.254

## 2. Masques

- 192.168.10.210/16
    - Réseau : 192.168.0.0/16
    - Première : 192.168.0.1
    - Dernière : 192.168.255.254
    - Broadcast : 192.168.255.255

- 172.31.48.120/24
    - Réseau : 172.32.48.0/24
    - Première : 172.32.48.1
    - Dernière : 172.32.48.254
    - Broadcast : 172.32.48.255

- 126.10.10.5/18
    - Réseau : 126.10.0.0/18
    - Première : 126.10.0.1
    - Dernière : 126.10.63.254
    - Broadcast : 126.10.63.255

## 3. Divisions

Masque /26 (/24 + 2 bits)

Sous-réseau 1 :

    Adresse réseau : 192.168.10.0
    Plage d'adresses utilisables : 192.168.10.1 à 192.168.10.62
    Adresse de diffusion : 192.168.10.63

Sous-réseau 2 :

    Adresse réseau : 192.168.10.64
    Plage d'adresses utilisables : 192.168.10.65 à 192.168.10.126
    Adresse de diffusion : 192.168.10.127

Sous-réseau 3 :

    Adresse réseau : 192.168.10.128
    Plage d'adresses utilisables : 192.168.10.129 à 192.168.10.190
    Adresse de diffusion : 192.168.10.191

Sous-réseau 4 :

    Adresse réseau : 192.168.10.192
    Plage d'adresses utilisables : 192.168.10.193 à 192.168.10.254
    Adresse de diffusion : 192.168.10.255

