# Procés complet de còpies de seguretat amb Linux i Duplicity

Al primer que farem serà veure el nom del disc, la mida, etc. Amb aquesta comanda:

lsblk -ol NAME,SIZE,TYPE,MOUNTPOINT  
![foto](IMG/1.jpg)

Ara el que farem serà muntar el disc (/dev/sda3) a /media/backup, comprovant que està muntat amb df -T, i instal·lant o verificant l’eina duplicity per fer les còpies de seguretat.  
![foto](IMG/2.jpg)

Ara el que farem serà afegir usuari2 amb la comanda:

sudo adduser usuari2  
![foto](IMG/3.jpg)

Entrarem com a root amb la comanda:

sudo su  
![foto](IMG/4.jpg)

Ara entrarem dins de duplicity amb la comanda:

sudo duplicity \  
--full-if-older-than 1W \  
/home \  
file:///media/backup/home_repo/

![foto](IMG/5.jpg)

Ara estem esborrant tots els fitxers .dat que comencen per “fitxer” del directori /home/usuari2, com a root, amb la comanda:

rm fitxer*.dat  
![foto](IMG/6.jpg)

Estem creant una carpeta de restauració i restaurant una còpia de seguretat amb duplicity des de /media/backup/home_repo/ cap a /home/usuari/restore_test. Durant el procés es demana la contrasenya GPG per desxifrar. Les comandes són:

mkdir -p /home/usuari/restore_test  
sudo duplicity \  
file:///media/backup/home_repo/ \  
/home/usuari/restore_test/

![foto](IMG/7.jpg)

Aquí el que faig és desmuntar el dispositiu de backup amb la comanda:

sudo umount /media/backup  
![foto](IMG/9.jpg)

Entrem com a root per tenir permisos, anem al directori de l’usuari i redimensiono un fitxer a 4 MB amb truncate. Després faig una còpia de seguretat del directori /home a un disc extern amb Duplicity, introdueixo la contrasenya GPG i comprovo que el backup es fa correctament.  
![foto](IMG/10.jpg)

Ara editem un script Bash amb nano (fullbackup.sh) per automatitzar una còpia de seguretat.  
![foto](IMG/11.jpg)

En la imatge següent podem veure que s’ha creat tot correctament.  
![foto](IMG/12.jpg)

Ara, per programar la temporització, escriurem:

sudo crontab -e  
![foto](IMG/13.jpg)  
![foto](IMG/14.jpg)
