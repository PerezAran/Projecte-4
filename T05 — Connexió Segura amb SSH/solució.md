# Accés Remot. Connexió via SSH

Aran Pérez Rigau

Al primer que hem de fer es crear 2 màquines Virtuals, una ubuntu server i una Windows.

Haurem de cambiar la configuració de la xarxa NAT d'aquesta manera, i posar un  adaptador en amfitrió, que serà desde on ens connectarem per ssh.

![foto](img/500.jpg) 
![foto](img/501.jpg) 

Hem de instalar shh en la màquina de ubuntu amb un sudo apt install shh -y.
![foto](img/502.jpg) 

Un cop fet això farem un ip a, i ens connectarem desde la màquina windows a la del servidor, per comprovar que ho hem fet bé.
![foto](img/503.jpg) 

## Configuració ssh:
AIXÒ HO FEM PER TENIR UNA LLISTA D'USUARIS AUTORITZATS I DESACTIVAR L'ACCÉS A ROOT  

Hem de entrar desde la màquina del servidor per configurar ssh, entrarem al seguent arxiu:  

`sudo nano /etc/ssh/sshd_config`  

I afegirem lo que posa a les captures:
![foto](img/505.jpg) 


Aquí estem dient que només pugui entrar usuari perquè crearem un 2n usuari i comprovarem que n pot entrar.
![foto](img/506.jpg) 


Ara hem de crear un usuari que es digui usuari2  i configurar que no es pugui connectar per ssh aquest usuari2.
![foto](img/507.jpg) 

Com poder veure usuari2, no te permis
![foto](img/508.jpg) 

## Part del túnel:

Ara ens connectarem des del nostre servidor, cap al client, amb un túnel SSH.
![foto](img/509.jpg) 

Ara entrarem a les propiedades d'internet, i farem el següent:
![foto](img/10.jpg) 

## Wireshark:

Instal·larem al Wireshark, a la màquina del Windows, i d'aquesta manera podrem veure els paquets ssh.
![foto](img/511.jpg) 
![foto](img/512.jpg) 

