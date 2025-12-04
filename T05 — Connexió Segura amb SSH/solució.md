# Accés Remot. Connexió via SSH

Aran Pérez Rigau

Al primer que hem de fer es crear 2 màquines Virtuals, una ubuntu server i una Windows.

Haurem de cambiar la configuració de la xarxa NAT d'aquesta manera, i posar un  adaptador en amfitrió, que serà desde on ens connectarem per ssh.

![foto](img/imatge500.jpg) 
![foto](img/imatge501.jpg) 

Hem de instalar shh en la màquina de ubuntu amb un sudo apt install shh -y.
![foto](img/imatge502.jpg) 

Un cop fet això farem un ip a, i ens connectarem desde la màquina windows a la del servidor, per comprovar que ho hem fet bé.
![foto](img/imatge503.jpg) 
![foto](img/imatge504.jpg) 

## Configuració ssh:
AIXÒ HO FEM PER TENIR UNA LLISTA D'USUARIS AUTORITZATS I DESACTIVAR L'ACCÉS A ROOT  

Hem de entrar desde la màquina del servidor per configurar ssh, entrarem al seguent arxiu:  

`sudo nano /etc/ssh/sshd_config`  

I afegirem lo que posa a les captures:
![foto](img/imatge505.jpg) 
![foto](img/imatge506.jpg) 

Aquí estem dient que només pugui entrar usuari perquè crearem un 2n usuari i comprovarem que n pot entrar.
![foto](img/imatge507.jpg) 
![foto](img/imatge508.jpg) 
![foto](img/imatge509.jpg) 

Ara hem de crear un usuari que es digui usuari2  i configurar que no es pugui connectar per ssh aquest usuari2.
![foto](img/imatge510.jpg) 

Com poder veure usuari2, no te permis
![foto](img/imatge511.jpg) 
![foto](img/COMODIN.jpg) 

## Part del túnel:

Ara ens connectarem des del nostre servidor, cap al client, amb un túnel SSH.
![foto](img/imatge512.jpg) 

Ara entrarem a les propiedades d'internet, i farem el següent:
![foto](img/imatge513.jpg)  ![foto](img/imatge514.jpg) 
![foto](img/imatge515.jpg)  ![foto](img/imatge516.jpg) 

## Wireshark:

Instal·larem al Wireshark, a la màquina del Windows, i d'aquesta manera podrem veure els paquets ssh.
![foto](img/imatge517.jpg) 
![foto](img/imatge518.jpg) 
![foto](img/imatge519.jpg) 
![foto](img/imatge520.jpg) 
