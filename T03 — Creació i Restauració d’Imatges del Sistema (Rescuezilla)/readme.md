# 💾 T03: DRP — Imatges del Sistema (Zorin OS)

### 🛡️ Pla de Recuperació davant Desastres i Continuïtat de Negoci

---

## 🎯 Context i Objectiu del Cas

Després de l'èxit en la recuperació i fortificació del portàtil anterior, el client ens encarrega un pilar crític del seu **Pla de Contingència**: assegurar que els treballadors puguin disposar d'un equip de treball operatiu de forma gairebé immediata en cas de robatori, pèrdua o avaria física.

Com que el temps de posada en marxa és crític, **no és viable** fer una instal·lació neta des de zero (SO, configuracions, aplicacions). S'ha d'implementar una solució basada en **imatges de restauració de disc complet** sobre l'entorn del client: **Zorin OS 18**.

---

## 📅 Estructura de la Tasca (Treball Individual)

```
┌────────────────────────────────────────┐       ┌────────────────────────────────────────┐
│ FASE 1: ANÀLISI I JUSTIFICACIÓ         │ ────> │ FASE 2: GUIA TÈCNICA (PoC)             │
│ Comparativa i elecció de l'eina        │       │ Creació i restauració amb Rescuezilla   │
└────────────────────────────────────────┘       └────────────────────────────────────────┘

```

---

## 📂 Desenvolupament de les Fases

### 📊 FASE 1: Anàlisi i Justificació de la Solució Tècnica

S'ha de realitzar un estudi de mercat comparant **4 solucions** per a la clonació i creació d'imatges de disc (especificant preu i característiques clau).

#### Taula Comparativa d'Eines

| Tipus de Solució | Nom del Producte | Característiques Destacades | Model de Preu / Llicència |
| --- | --- | --- | --- |
| **Comercial 1** | *[Ex: Acronis Cyber Protect]* |  |  |
| **Comercial 2** | *[Ex: Clonezilla Pro / Macrium]* |  |  |
| **Comunitat 1** | *[Ex: Clonezilla (Open Source)]* |  |  |
| **Comunitat 2** | *[Ex: Rescuezilla]* |  |  |

> 🧠 **Proposta Final Justificada:** Redacta una conclusió raonada triant l'eina ideal per al client, posant en balança els costos, la simplicitat d'ús i el temps de recuperació.

---

### 🛠️ FASE 2: Guia d'Ús Tècnica (Manual Operatiu)

Prova de Concepte (PoC) pràctica utilitzant una màquina virtual (**OVA**) amb Zorin OS 18. Per a aquesta demo s'utilitzarà **Rescuezilla**.

#### 📝 Processos clau a documentar:

1. **Creació de la imatge completa:** Captura de tot el disc de la màquina original de forma sector a sector o optimitzada.
2. **Restauració sobre un sistema net:** Abocament de la imatge en una màquina virtual idèntica de destí (sense SO preinstal·lat).

#### 📋 Requisits del Document Tècnic:

* [ ] Passos detallats d'arrencada des del Live ISO de Rescuezilla.
* [ ] Captures de pantalla significatives de l'assistent (selecció de disc origen/destí, rutes d'emmagatzematge).
* [ ] Verificació final que el sistema arrenca correctament amb tot el programari tal com estava.

---

## 🔗 Materials i Links de Suport

* 🛡️ **INCIBE:** [¿Ya tienes tu Plan de Recuperación ante Desastres?](https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres)
* 🦎 **Eina de Treball:** [Pàgina oficial de Rescuezilla](https://rescuezilla.com/)
