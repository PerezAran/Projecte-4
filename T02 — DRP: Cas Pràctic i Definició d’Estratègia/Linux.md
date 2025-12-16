# Linux

## Identificació del disc
El primer que farem serà veure el nom del disc, la mida, el tipus i el punt de muntatge amb la següent comanda:

`lsblk -ol NAME,SIZE,TYPE,MOUNTPOINT`

![foto](IMG/1.jpg)

## Muntatge del disc i instal·lació de Duplicity
Ara el que farem serà muntar el disc (`/dev/sda3`) a `/media/backup`, comprovar que està muntat amb `df -T`, i instal·lar/verificar l’eina **duplicity** per fer les còpies de seguretat.

![foto](IMG/2.jpg)

## Creació d’un nou usuari
Ara afegirem l’usuari **usuari2** amb la comanda:

`sudo adduser usuari2`

![foto](IMG/3.jpg)

## Accés com a root
Entrarem com a **root** amb la comanda:

`sudo su`

![foto](IMG/4.jpg)

## Còpia de seguretat amb Duplicity
Ara entrarem dins de Duplicity amb la comanda:

```bash
sudo duplicity \
--full-if-older-than 1W \
/home \
file:///media/backup/home_repo/

