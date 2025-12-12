# Part 1: Còpia de seguretat dels equips clients Windows

## 1. Creació de la màquina virtual
- Crear una **VM amb Windows 11**.
- Afegir **dos discos**:
  - Un per al sistema.
  - Un disc secundari de **10 GB**.

**Per què?**  
El segon disc simula un dispositiu local dedicat a còpies de seguretat.

![foto](IMG/1.jpg) 

---

## 2. Instal·lació de Duplicati
- Descarregar i instal·lar **Duplicati**.

![foto](IMG/2.jpg) 

---

## 3. Configuració del pla de còpies
Crear **dos plans de còpia**:

- **Cada hora** → cap al disc secundari.  
- **A les 18:00** → cap a **Google Drive** (amb un compte específic).

![foto](IMG/3.jpg) 

![foto](IMG/4.jpg) 

---

## 4. Validació del funcionament
- Afegir arxius a *Documents* i comprovar que es copien.
- Esborrar *Documents* i **restaurar** des del disc secundari.
- Restaurar també des de **Google Drive**.
![foto](IMG/5.jpg) 

---
