Aquí tens un resum clar, estructurat, visual i bonic en format **Markdown** per a la teva tasca de seguretat informàtica. Està pensat per utilitzar-lo com a guia de treball o plantilla de lliurament.

---

# 📑 T01: DRP — Còpies de Seguretat

### 🏢 Estudi de Cas Client: *Muntatges i Serveis Tècnics SL*

---

## 🎯 Objectiu de la Tasca

Dissenyar i implementar un **Pla de Recuperació davant Desastres (DRP)** centrat en les còpies de seguretat per a una petita empresa, aplicant la **regla 3-2-1** i garantint els objectius de recuperació (**RTO** i **RPO**).

---

## 💻 1. Diagnòstic del Client

### 📊 Infraestructura Tècnica

* **Servidor de Fitxers (Ubuntu Server):** *Total: 420 GB*
* 📂 **Projectes:** Plànols i especificacions (300 GB, creixement moderat).
* 🗄️ **Bases de Dades (BD):** Comptabilitat i Clients (**20 GB, Crític, canvi constant**).
* 👤 **Carpetes Personals:** Feina diària dels usuaris (100 GB).


* **Equips Clients:** 10 ordinadors (Windows 10/11) amb informes temporals a la carpeta *Documents*.
* **Connexió:** Fibra òptica simètrica de **600 Mbps**.

### ⏱️ Requisits de Recuperació (SLA)

| Dada / Servei | RTO (Temps de Recuperació) | RPO (Pèrdua admissible) | Retenció |
| --- | --- | --- | --- |
| **Comptabilitat i Clients (BD)** | ⏱️ **< 4 hores** | 📉 **< 4 hores** | 🗓️ 1 mes mínim |
| **Resta de dades (Projectes/Usuaris)** | 🕒 Estàndard | 📉 **< 24 hores** | 🗓️ 1 mes mínim |

---

## 🔄 2. Fases de la Dinàmica Cooperativa

```
┌─────────────────────────┐      ┌─────────────────────────┐      ┌─────────────────────────┐
│  FASE 1: INDIVIDUAL     │ ───> │   FASE 2: PARELLES      │ ───> │    FASE 3: GRUP TOT     │
│ Respostes i justificació│      │ Debat i Esquema 3-2-1   │      │ Política i Document     │
└─────────────────────────┘      └─────────────────────────┘      └─────────────────────────┘

```

### 👤 FASE 1: Treball Individual (Preguntes Clau)

1. **Què copiar?** Priorització de les dades de l'Ubuntu Server vs. els 10 equips Windows.
2. **Periodicitat i Tipus:** Proposta de calendari setmanal (Completa, Diferencial, Incremental).
3. **Mitjans i Ubicació:** Elecció del suport (NAS, Cloud, Disc Extern) aplicant la regla 3-2-1.

### 👥 FASE 2: Treball per Parelles (Consens)

*Ompliu aquesta taula combinant les millors idees de cadascú:*

| Element | Proposta de la Parella | Justificació (Per què?) |
| --- | --- | --- |
| **Dades Crítiques** |  | *Prioritat absoluta per negoci.* |
| **Periodicitat (BD)** |  | *Per complir RPO < 4h.* |
| **Tipus de Còpia (BD)** |  | *Equilibri velocitat/espai.* |
| **Mitjà 1 (Local)** |  | *Recuperació ràpida (RTO).* |
| **Mitjà 2 (Extern)** |  | *Protecció contra incendis/robatori.* |

---

## 📄 3. Document Final (FASE 3: Grup)

> 💡 *Aquesta és la proposta final que es presentarà a l'empresa Muntatges i Serveis Tècnics SL.*

### 1) Dades Objecte de Còpia

* **Còpies Crítiques (Servidor):** Bases de dades (Comptabilitat/Clients) cada 4 hores.
* **Còpies Estàndard (Servidor):** Projectes i Carpetes d'Usuaris de forma diària.
* **Equips Clients (Windows):** *Estratègia de grup (ex: Sincronització amb el servidor o exclusió).*

### 2) Cronograma Setmanal Detallat

| Dia | Dades (Ex: BD, Projectes...) | Tipus de Còpia | Mitjà (Local / Clar) |
| --- | --- | --- | --- |
| **Dilluns** |  |  |  |
| **Dimarts** |  |  |  |
| **Dimecres** |  |  |  |
| **Dijous** |  |  |  |
| **Divendres** |  |  |  |
| **Dissabte** |  |  |  |
| **Diumenge** |  |  |  |

### 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

* **Còpies Totals:** **3 còpies** (1 viva en producció + 2 ràpides de seguretat).
* **Mitjà 1 (Local):** `[Ex: NAS en xarxa local / Disc dur USB professional]`
* **Mitjà 2 (Extern / Cloud):** `[Ex: Proveïdor Cloud (Azure / AWS / Google Cloud)]`
* **Ubicació Fora de Lloc:** `[Física o lògica]` i **Responsable de la gestió:** `[Nom/Rol del perfil]`.

### 4) Estratègia de Recuperació (Garantia RTO/RPO)

* **Com es garanteix el RPO de 4h?** Mitjançant còpies incrementals de la BD cada 4 hores durant la jornada laboral.
* **Com es garanteix el RTO de 4h?** Mitjançant la restauració des del **Mitjà 1 (Local)** que aprofita els 600 Mbps de la xarxa interna per minimitzar el temps de baixada.

---

## 📚 Materials de Suport

* 🌐 **Moodle:** *Seguretat Informàtica. RA2.AA3 Còpies*
* 🛡️ **INCIBE:** *Guía de aproximación para el empresario.*
* 📺 **Xataka Video:** [Backup 3-2-1, el método definitivo](https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8)