# Part 1: Còpia de seguretat dels equips clients Windows

## 1. Creació de la màquina virtual
- Crear una **VM amb Windows 11**.
- Afegir **dos discos**:
  - Un per al sistema.
  - Un disc secundari de **10 GB**.

**Per què?**  
El segon disc simula un dispositiu local dedicat a còpies de seguretat.

---

## 2. Instal·lació de Duplicati
- Descarregar i instal·lar **Duplicati**.

**Per què?**  
És una eina gratuïta que permet fer còpies locals i al núvol amb programació horària.

---

## 3. Configuració del pla de còpies
Crear **dos plans de còpia**:

- **Cada hora** → cap al disc secundari.  
- **A les 18:00** → cap a **Google Drive** (amb un compte específic).

**Per què?**  
Segueix l’esquema **3-2-1**:
- 3 còpies  
- 2 suports diferents  
- 1 còpia fora de l’empresa

---

## 4. Validació del funcionament
- Afegir arxius a *Documents* i comprovar que es copien.
- Esborrar *Documents* i **restaurar** des del disc secundari.
- Restaurar també des de **Google Drive**.

---
