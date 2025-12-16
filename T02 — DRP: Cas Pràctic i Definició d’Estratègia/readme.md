# T02: DPR: Còpies de seguretat. Cas pràctic

## Breu descripció

### Introducció al cas
A la tasca anterior heu dissenyat una política de còpies de seguretat pel nou client **"Muntatges i Serveis Tècnics SL"**. Ara toca portar a la pràctica l’estudi anterior. El client demana que s’elaborin unes guies tècniques amb proves de concepte perquè el seu personal estigui qualificat per implantar el pla de còpies de seguretat.

---

## Part 1: Còpia de seguretat dels equips clients Windows

Encara que en principi el DPR no contemplaria fer còpia dels arxius locals dels equips clients, se’ns demana fer una excepció amb l’equip Windows del director de l’empresa. En aquest equip es guarda informació important que no es vol tenir accessible al servidor de fitxers de l’empresa. 

Es defineix una política de còpies de seguretat seguint l’esquema **3-2-1**:
- Una còpia a un **disc secundari** que té l’equip.
- Una còpia al **cloud** (Google Drive) amb l’eina **Duplicati**.

Com a prova de concepte:
1. Creeu una màquina virtual **Windows 11** amb dos discos: 
   - Un per al sistema.
   - Un de secundari de 10 GB per emmagatzemar les còpies.
2. Simuleu Google Drive amb un compte específic (no escolar).
3. Configureu còpies del perfil de l’usuari:
   - Cada hora al disc secundari.
   - A les 18:00 a Google Drive.

**Procediment:**
- Documenteu la instal·lació de Duplicati.
- Configureu els plans de còpia.
- Afegiu arxius a les carpetes de l’usuari (especialment `Documents`).
- Esborreu el contingut de `Documents` i restaureu des del disc secundari.
- Comproveu la restauració des del cloud.

---

## Part 2: Còpia de seguretat del servidor Linux

Per fer les còpies del servidor Linux es proposa **Duplicity**, que permet fer còpies contra mitjans locals o remots. Combinat amb **cron**, es poden implementar polítiques de còpia.

**Prova de concepte:**
1. VM amb **Ubuntu Server** i un segon disc de 10 GB com a unitat auxiliar.
2. Inicialitzeu i formateu a **XFS**, muntant-lo manualment a `/media/backup`.
3. Instal·leu **Duplicity**.
4. Creeu un parell d’usuaris amb carpeta personal. Creeu 4 arxius de 10 MB a `/home`.
5. Feu una còpia de seguretat de `/home`.
6. Esborreu els arxius i feu un **restore** per comprovar la recuperació.
7. Afegiu un fitxer de 4 MB i feu una còpia incremental.
8. Desmunteu la unitat de backup.

**Automatització amb scripts i cron:**
- La unitat de backup ha d’estar **desmuntada per defecte**. El primer pas de l’script ha de muntar la unitat i l’últim desmuntar-la.

1. Creeu un script `fullbackup.sh` per fer una còpia completa de `/home` al volum muntat.  
   - Feu servir la variable d’entorn `PASSPHRASE` per no haver d’introduir la contrasenya durant l’execució.  
   - Doneu permisos d’execució.
2. Programeu al **cron** l’execució de l’script **diumenges a les 23:00**.
3. Creeu un segon script `incrementalbackup.sh` per fer còpies incrementals.  
   - Fixeu `PASSPHRASE` com abans i doneu permisos d’execució.
4. Programeu al **cron** l’execució **dilluns a dissabte a les 23:00**.

---

## Materials i links de suport

- **Duplicati:** [https://duplicati.com/](https://duplicati.com/)
- **Crear arxius amb fsutil (Windows):** [WayToIT Blog](https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/)
- **Crear arxius de prova a Linux:** [WayToIT Blog](https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/)
- **Duplicity man page:** [http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html](http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html)
- **Programació de tasques amb cron:** [https://geekytheory.com/programar-tareas-en-linux-usando-crontab](https://geekytheory.com/programar-tareas-en-linux-usando-crontab)

