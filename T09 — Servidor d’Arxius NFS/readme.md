# **Projecte04: Servidor NFS**

## **El Cas Client: DevOptimize Solutions**

El nostre client, DevOptimize Solutions, és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Tenen un problema crític: el seu codi font i els seus actius (documents de disseny, scripts) estan descontrolats. Cada desenvolupador té còpies locals, cosa que provoca errors de versió constants i una pèrdua d'eficiència brutal. Ens han contractat per implementar un servidor de fitxers centralitzat. Atès que tot l'entorn és Linux, la solució nativa, més ràpida i eficient del sector és NFS (Network File System). El client ha insistit en que treballa sense un entorn d’autenticació centralitzada i que, de moment, no té previst fer aquest pas.

Per mostrar al client com quedarà la solució proposada a partir de les seves demandes i poder mostrar també les seves limitacions, se t’encarrega fer una demostració del sistema.

Crearàs un servidor NFS (NFSv3) i un client Linux que consumeixi els recursos compartits. Hauràs de crear usuaris i grups per simular l'entorn del client i demostrar el control d'accés utilitzant les opcions d'exportació (/etc/exports) i els permisos del sistema de fitxers (chmod, chown).

---

# **Fases del projecte**

## **Fase 1: Preparació de l'entorn**

Per preparar aquesta prova de concepte, necessitaràs dues màquines virtuals Linux: tot i que pel servidor podríem fer servir qualsevol distribució, ens decantarem per Ubuntu Server 24.04 LTS per la seva facilitat d'ús i popularitat. Per al client, utilitzarem Zorin OS 18. Els dos equips els configurarem amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor.

Tots dos equips els instal·larem seguint els requisits recomanats. L'idioma triat serà espanyol (Espanya) i amb l'idioma per defecte en espanyol. En el cas d'Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.

Ens assegurarem que ambdues màquines tinguin accés a Internet i que es puguin comunicar entre elles a través de la xarxa només-amb-amfitrió i actualitzarem els sistemes amb les últimes actualitzacions disponibles.

---

## **Fase 2: Preparació del servidor**

Abans de compartir res, hem de preparar els usuaris i els directoris al Servidor.

### **Creació de Grups**
Crear dos grups per al client: devs i admins.

### **Creació d'Usuaris**
Crear un usuari dev01 (membre del grup devs).  
Crear un usuari admin01 (membre del grup admins).

### **Creació de Directoris (al Servidor)**

Crear el directori per als projectes de desenvolupament: `/srv/nfs/dev_projects`  
Crear el directori per a les eines d'administració: `/srv/nfs/admin_tools`

### **Permisos del Servidor (El punt clau)**

- Es vol que els developers tinguin control total sobre els seus projectes.
- Es vol que els administradors tinguin control sobre les seves eines.
- En tots dos casos, l'usuari propietari serà root.

Com a pas final, s'instal·laran els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.

**Nota:** Perquè aquesta pràctica funcioni correctament, heu de replicar aquests usuaris i grups al client, o, idealment, assegurar-vos que els UID i GID coincideixin a les dues màquines.

---

## **Fase 3: L'Exportació d'Administració (El Dilema del root_squash)**

El client necessita que el directori `/srv/nfs/admin_tools` sigui accessible per l'equip d'administradors. A vegades, l'usuari root del client necessitarà escriure en aquest directori per instal·lar altres eines. Aquí mostrarem un error típic i la seva solució.

### **Prova 1 (L'error comú)**

- Exportar el directori `/srv/nfs/admin_tools` amb les opcions `rw,sync`.
- Des del client, muntar aquest recurs compartit a `/mnt/admin_tools`.
- Com a root del client, intentar crear un fitxer dins d'aquest directori muntat.
- Verificar quin és el propietari del fitxer creat.
- Justificar la resposta amb l'explicació tècnica de *root_squash*.

### **Prova 2 (La Solució)**

- Modificar l'exportació del directori `/srv/nfs/admin_tools` per incloure l'opció `no_root_squash`.
- Al client, desmuntar i tornar a muntar el recurs compartit.
- Com a root del client, intentar crear un fitxer dins d'aquest directori muntat.
- Analitzar el canvi de propietari i justificar-lo amb *no_root_squash*.

---

## **Fase 4: L'Exportació de Desenvolupament (Permisos rw vs ro)**

- Editar `/etc/exports` per afegir dues exportacions per al mateix directori.
- La xarxa d'administració (192.168.56.0/24) pot escriure.
- La xarxa de consultors (192.168.56.100) només pot llegir.

### **Proves**

- Muntar `/mnt/dev_projects` com dev01 i provar d'escriure.
- Canviar IP del client a `192.168.56.100` i tornar a provar → només lectura.
- Canviar a usuari admin01 → no pot escriure perquè no és del grup devs.

---

## **Fase 5: Muntatge Automàtic amb /etc/fstab**

- Editar `/etc/fstab` per muntar automàticament els recursos NFS.
- Executar `mount -a` per verificar.
- Reiniciar i comprovar que s'han muntat correctament.

---

# **Conclusió**

En aquesta prova de concepte s'ha demostrat el funcionament amb els requisits que ha demanat l'empresa client, però ja ets un tècnic prou experimentat per saber que aquesta solució té moltes limitacions i problemes de seguretat. Quines recomanacions faries al client per millorar aquesta solució en un futur? Pensa en termes d'autenticació centralitzada i gestió d'usuaris i permisos.

---

# **Com lliurar la tasca**

Documenta tot el procés seguint les fases descrites anteriorment.

Per les comandes, escriu-les com a codi. Exemple:

