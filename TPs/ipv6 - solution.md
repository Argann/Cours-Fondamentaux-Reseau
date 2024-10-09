## 1. Hexadécimal

- 0001 0010
- 0001 1010
- 1111 1111
- 1100 0011

- ca
- fe
- D6
- 14

## 2. forme simplifiée

- 2001:db8::ff00:42:8329
- fe80::202:b3ff:fe1e:8329
- 2001:db8:0:2b1c::1
- ff02::aa14:0:2

## 3. Catégories

- Une adresse multicast fait toujours partie de "ff00::/8"
- ff02::1 (tous les noeuds sur le réseau local)

## 4. découpage

Subnet ID	Subnet Address	Host Address        Range	             Notation
1	2001:0db8::	        2001:db8::      - 2001:db8:1fff:ffff::	2001:db8::/35
2	2001:0db8:2000::	2001:db8:2000:: - 2001:db8:3fff:ffff::	2001:db8:2000::/35
3	2001:0db8:4000::	2001:db8:4000:: - 2001:db8:5fff:ffff::	2001:db8:4000::/35
4	2001:0db8:6000::	2001:db8:6000:: - 2001:db8:7fff:ffff::	2001:db8:6000::/35
5	2001:0db8:8000::	2001:db8:8000:: - 2001:db8:9fff:ffff::	2001:db8:8000::/35
6	2001:0db8:a000::	2001:db8:a000:: - 2001:db8:bfff:ffff::	2001:db8:a000::/35
7	2001:0db8:c000::	2001:db8:c000:: - 2001:db8:dfff:ffff::	2001:db8:c000::/35
8	2001:0db8:e000::	2001:db8:e000:: - 2001:db8:ffff:ffff::	2001:db8:e000::/35