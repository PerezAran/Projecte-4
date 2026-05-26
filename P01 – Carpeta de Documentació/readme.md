Aquí tens el resum estructurat, visual i optimitzat en format **Markdown** per a aquesta segona tasca de col·laboració amb GitHub. Està dissenyat amb la mateixa estètica professional per al teu repositori o apunts.

---

# 🐙 P01: GitHub Col·laboratiu — Forks i Pull Requests

### 🚀 Procés d'Onboarding Professional a *EverPia*

---

## 🎯 Objectiu de la Tasca

Simular el flux de treball d'una consultora tecnològica real. L'objectiu és dominar el treball en equip amb Git i GitHub mitjançant l'ús de **Forks**, branques i **Pull Requests (PR)** amb revisió de codi, evitant males pràctiques com treballar directament a `main`.

---

## 👥 Rols de l'Equip

Dins del grup de treball habitual, es dividiran les funcions en dos rols clau:

* **👑 Team Leader (Líder d'Equip):** S'encarrega de gestionar el repositori, revisar el codi aportat pels companys i aprovar o rebutjar les integracions.
* **💻 Membres de l'Equip (Consultors Júniors):** S'encarreguen de desenvolupar la feina a les seves pròpies còpies (forks) i sol·licitar la integració de canvis.

---

## 🔄 El Flux de Treball a *EverPia* (Workflow)

```
[ Repositori Base Central ] (SMX2n/EverPia-Onboarding)
            │
            ▼  (Fork)
[ El teu GitHub Personal ]
            │
            ▼  (Clone)
[ Màquina Local / Servidor ] ───> (Crear branca -> Modificar fitxers -> Commit)
            │
            ▼  (Push)
[ El teu GitHub Personal ]
            │
            ▼  (Pull Request)
[ Repositori Base Central ] ───> 👑 Reviso del Team Leader ───> ✅ MERGE!

```

---

## 🛠️ Passos per a l'Execució de la Tasca

### 📑 Pas 1: Preparació del Repositori (Fork & Clone)

1. **Fer un Fork:** Cada membre de l'equip ha d'anar al repositori base i fer un *Fork* cap al seu compte personal de GitHub.
2. **Clonar:** Clonar el repositori forkejat a la màquina local o servidor de treball:
```bash
git clone https://github.com/EL_TEU_USUARI/EverPia-Onboarding.git

```



### 🌿 Pas 2: Treball en una Branca (Branch & Commit)

1. **Crear una branca:** No es treballa mai a `main`. Es crea una branca específica per a la tasca (per exemple, `feature-onboarding-aran`).
```bash
git checkout -b feature-onboarding-aran

```


2. **Modificacions:** Realitzar els canvis o afegir els fitxers de configuració requerits segons la guia.
3. **Commit:** Desar els canvis de forma local amb un missatge clar i descriptiu.
```bash
git add .
git commit -m "Add: configuració inicial onboarding per a perfil tècnic"

```



### 🚀 Pas 3: Pujada i Sol·licitud d'Integració (Push & Pull Request)

1. **Pujar la branca:** Enviar la branca creada al teu GitHub remot.
```bash
git push origin feature-onboarding-aran

```


2. **Obrir Pull Request (PR):** Des de la interfície de GitHub, obrir un *Pull Request* des de la teva branca cap a la branca del repositori central de l'empresa.

### 👑 Pas 4: Revisió de Còdi (Code Review & Merge)

* El **Team Leader** rebrà la notificació de la PR.
* Haurà d'analitzar els canvis, comprovar que tot estigui correcte (sense errors de sintaxi ni fitxers brossa) i, si tot és correcte, fer el **Merge** per integrar-ho al projecte final de l'empresa.

---

## 🔗 Recursos i Enllaços de Suport

* 🏢 **Repositori Base (EverPia-Core):** [SMX2n/EverPia-Onboarding](https://github.com/SMX2n/EverPia-Onboarding)
* 📖 **Guia Oficial de l'Activitat:** [Projecte04-GuiaGitHub](https://github.com/SMX2n/Projecte04-GuiaGitHub)
