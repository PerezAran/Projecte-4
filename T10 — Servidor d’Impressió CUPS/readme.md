Aquí tens el resum visual, estructurat i polit en format **Markdown** per a la tasca **T10**. Manté el mateix estil professional, clar i organitzat que els anteriors, ideal per fer-lo servir com a guia durant la pràctica o com a plantilla del teu lliurament individual.

---

# 🖨️ T10: Servidor d'Impressió Linux — CUPS

### 🛠️ Prova de Concepte (PoC) per a *DevOptimize Solutions*

---

## 🎯 Context i Objectiu de la Tasca

El client, *DevOptimize Solutions*, necessita resoldre el caos de gestió, drivers i costos derivat de les seves impressores d'oficina. La solució plantejada és la implementació d'un **Servidor d'Impressió Centralitzat**.

L'objectiu és realitzar una **Prova de Concepte (PoC)** utilitzant el sistema de codi obert **CUPS** (Common UNIX Printing System). Per simular l'entorn de xarxa sense requerir maquinari físic, s'utilitzarà la impressora virtual `cups-pdf`, la qual generarà un fitxer PDF al servidor per cada feina d'impressió enviada des del client.

---

## 💻 Escenari de Treball (Xarxa)

S'utilitzarà la mateixa infraestructura de màquines virtuals que a la PoC de NFS:

* **🖥️ Servidor (Ubuntu Server):**
* Interfície 1: NAT (Accés a Internet).
* Interfície 2: Xarxa *Host-Only* (Xarxa interna de treball).


* **💻 Client (Zorin OS Desktop):**
* Mateixa configuració de xarxa que el servidor per garantir la visibilitat mutua.



---

## 🔄 Passos per a l'Execució de la PoC

El flux pràctic s'estructura en els següents set punts clau:

```
[ 1. Instal·lar CUPS ] ──> [ 2. Afegir cups-pdf ] ──> [ 3. Permetre Escoltar Xarxa ]
                                                               │
[ 6. Prova d'Impressió ] ◄── [ 5. Vincular a Zorin ] ◄── [ 4. Compartir via Web GUI ]
            │
            ▼
[ 7. Verificar PDF al Server ] 🏆

```

1. **Instal·lació:** Desplegar el servei CUPS a l'Ubuntu Server.
2. **Impressora Virtual:** Instal·lar el mòdul de generació de PDFs (`cups-pdf`).
3. **Escolta de Xarxa:** Configurar l'arxiu principal de CUPS perquè el dimoni escolti peticions per totes les interfícies de xarxa.
4. **Administració Web:** Accedir al tauler web de CUPS des del navegador, gestionar els permisos de seguretat i marcar la impressora com a **compartida**.
5. **Configuració del Client:** Afegir la impressora de xarxa compartida des de l'entorn gràfic de Zorin OS.
6. **Validació:** Enviar diferents documents a imprimir des del client cap al servidor.
7. **Auditoria:** Comprovar al directori del servidor que els arxius PDF s'han generat correctament i corresponen a les feines llançades.

---

## 📋 Requisits de Documentació

La memòria es lliura de forma individual i ha d'incloure:

* [ ] Totes les comandes utilitzades al terminal de forma polida (com a la tasca del PDF).
* [ ] Captures de pantalla significatives de la interfície web de CUPS.
* [ ] Evidència visual que el document enviat des de Zorin OS s'ha transformat en un PDF emmagatzemat correctament a l'Ubuntu Server.

---

## 🔗 Materials i Links de Suport

* 📁 **Moodle:** `UD5. AA1. CUPS` (Mòdul de **Sistemes Operatius en Xarxa**).
* 📺 **Video Tutorial:** [Instalación de servidor de impresión en CUPS para Linux](https://www.youtube.com/watch?v=FNwSTrOSgZQ)
* 📖 **Documentació d'Ubuntu:** [Network File System (NFS) Base Reference](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)
* 🌐 **Guia Tècnica:** [How To Install CUPS Print Server on Ubuntu 24.04 LTS (idroot)](https://idroot.us/install-cups-print-server-ubuntu-24-04/)
