---
title: Binaire et calcul en base 2
author: Argann BONNEAU
description: Présentation du calcul en base 2.
keywords: binaire, bit, octets, introduction
lang: fr

marp: true
theme: uncover
class: invert
paginate: true
header: Binaire et calcul en base 2
---

<!-- _paginate: false -->
<!-- _header: "" -->
<!-- _footer: "Ce cours a été rédigé par [Argann BONNEAU](https://argann.me) et est sous license [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)" -->

# Binaire et calcul en base 2

---

## 1. Base 10

---

Nous utilisons pour compter un système que nous appelons "**base 10**", c'est à dire que nous pouvons représenter tous les nombres possibles en utilisant 10 caractères (ou _chiffres_) (0, 1, 2, 3, 4, 5, 6, 7, 8 et 9).

---

Un **nombre** est composé d'un ou plusieurs chiffres.

"8" est un nombre.
"764132" est aussi un nombre.

---

Dans cette base, le nombre "974" peut également être représenté comme ceci :

$9\times10^2 + 7\times10^1 + 4\times10^0$

Chaque chiffre est multiplié par $x^i$, où $x$ est la base utilisée et $i$ est l'index du chiffre dans le nombre.

---

## 2. Base 2

---

Un ordinateur ne connaît pas tous nos chiffres ! En réalité, il n'en connaît que deux : 0 et 1.

On dit donc logiquement qu'il utilise la "**Base 2**" (ou plus communément appelé le "_binaire_").

---

Le principe est exactement le même que pour la base 10, avec juste moins de chiffres !

0, puis 1, puis 10, puis 11, puis 100, puis 101, etc.

---

Pour transformer un nombre de la base 2 à la base 10, on peut appliquer la même formule que tout à l'heure !

Par exemple, pour le nombre binaire 1101 :

$1101 = 1\times2^3 + 1\times2^2 + 0\times2^1 + 1\times2^0$
$1101 = 1\times8 + 1\times4 + 0\times2 + 1\times1$
$1101 = 8 + 4 + 1$
$1101 = 13$

---

**Question** : Combien vaut le nombre binaire "11010" en base 10 ?

<!-- Réponse : 16 + 8 + 2 = 26 -->

---

## 3. Représentations de nombres

---

En informatique, un nombre est _toujours_ stocké sur un certain nombre de _bits_. 

Cette taille limite le nombre pouvant être représenté.

---

Par exemple, le plus grand nombre pouvant être stocké sur 8 bits (ou un "_octet_") est :

$1111\space1111$, soit 255 en base 10.

**Un nombre stocké sur 8 bits ne pourra donc pas dépasser 255**.

---

Heureusement, augmenter le nombre de bits disponibles, c'est augmenter _drastiquement_ le nombre maximal pouvant être stocké !

| Taille (bits) | Nombre maximal (base 10)   |
|---------------|----------------------------|
| 8             | 255                        |
| 16            | 65 535                     |
| 32            | 4 294 967 295              |
| 64            | 18 446 744 073 709 551 615 |

---

Pour le moment, tous nos nombres binaires sont des entiers positifs (qu'on appelle en informatique des _entiers non-signés_).

Comment faire pour représenter un nombre négatif ?

---

**Méthode 1 : Bit de signe**
On prend le "bit le plus à gauche" : s'il vaut 0, le nombre est positif, s'il vaut 1, le nombre est négatif.

$0010 = 2$, $1010 = -2$

---

**Problème !**

Avec cette méthode, que vaut $0000$ ?

Et que vaut $1000$ ?

---

**Méthode 2 : Complément à deux**
Pour représenter un nombre négatif :
1. On prend sa valeur absolue
2. On inverse chaque bit
3. On ajoute 1.

Avec cette méthode, nous n'avons qu'un seul zéro : $0000$

---

**Exemple : $-4$**

1. Sa valeur absolue, c'est $4$ (donc $0100$)
2. On inverse tous les bits : $1011$
3. On ajoute 1 : $1100$

Avec cette méthode, -4 vaut en binaire $1100$.

---

| # bits | Min-Max (non-signé) | Min-Max (signé)                 |
|--------|---------------------|---------------------------------|
| 8      | 0 - 255             | -128 - 127                      |
| 16     | 0 - 65 535          | -32 768 - 32 767                |
| 32     | 0 - 4 294 967 295   | -2 147 483 648 - 2 147 483 647  |

---

OK, super... Et pour les nombres à virgule ?

---

Deux familles de solutions :

- **Virgule fixe** : On coupe le nombre binaire en deux : la partie de gauche pour la partie entière du nombre, et celle de droite pour la partie décimale (ou d'autres solutions plus complexes)
- **Virgule flottante** : IEEE 754 

---

## 4. Opérations binaires

---

Toutes les opérations classiques de base 10 fonctionnent avec la même logique en base 2.

Une addition, par exemple :

$$
\begin{align}
1101& \\
\underline{+\quad 1011}& \\
11000
\end{align}
$$

---

Il existe des opérations supplémentaires spécifiques à la base 2, qui sont _très_ utiles en informatique.

---

L'opérateur `~` (NON) inverse chaque bit d'un nombre (1 si le bit est à 0, 0 si le bit est à 1)

$\sim1011 = 0100$

---

L'opérateur `&` (ET) prend deux nombres binaires, et les comparent bit par bit, renvoyant pour chaque paire de bit 1 si les deux valent 1, 0 sinon.

$$
\begin{align}
1101& \\
\underline{\&\quad 1001}& \\
1001
\end{align}
$$

---

L'opérateur `|` (OU) prend deux nombres binaires, et les comparent bit par bit, renvoyant pour chaque paire de bit 1 si au moins l'un des deux vaut 1, 0 sinon.

$$
\begin{align}
1101& \\
\underline{|\quad 1001}& \\
1101
\end{align}
$$

---

L'opérateur `<<` (Décalage bit-à-bit vers la gauche) permet de décaler les bits d'un nombre d'un certain nombre d'emplacements vers la gauche.

$1011 << 2 = 1100$

(Il existe également l'opérateur de décalage vers la droite `>>`)

---

**Astuce :** décaler les bits vers la gauche d'un emplacement permet de multiplier par deux un nombre non signé !

Par exemple : 
$0010\space0100$ vaut 36
$0010\space0100 << 1 = 0100\space1000$
$0100\space1000$ vaut 72 (donc $2\times36$)

---