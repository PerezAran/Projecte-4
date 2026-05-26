Aquí tens el resum visual, net i en format **Markdown** per a la tasca **T08**. Està estructurat de manera que quedi ben clara la diferència entre la preparació pràctica i el repte de la certificació, ideal per tenir-ho com a referència d'estudi.

---

# 🛡️ T08: Auditoria de Qualitat i Estandardització de Servidors

### 📋 Protocol de Desplegament Estàndard (SOP — *Standard Operating Procedure*)

---

## 🎯 Context i Objectiu de la Tasca

Després d'implementar serveis complexos (NFS, CUPS, LDAP), és indispensable assegurar que els fonaments del sistema operatiu siguin totalment sòlids. Un servidor amb paquets obsolets, permisos vulnerables o mala configuració de xarxa és un risc crític.

La missió és consolidar la base mitjançant el **SOP** de l'empresa, garantint que qualsevol nova màquina virtual (**Ubuntu Server**) es desplegui des de zero amb els màxims estàndards de qualitat, robustesa i seguretat abans de passar a producció.

---

## 📅 Flux del Procés: Entrenament i Validació

```
┌────────────────────────────────────────┐       ┌────────────────────────────────────────┐
│ 🏋️ FASE D'ENTRENAMENT (Pràctica)       │ ────> │ 🎓 CERTIFICACIÓ (Examen Pràctic)        │
│ Desplegament basat en Projecte4-TascaSOP│       │ Validació oficial com a SOP Specialist  │
└────────────────────────────────────────┘       └────────────────────────────────────────┘

```

---

## 🔍 Detall de les Fases

### 🏋️ 1. Fase d'Entrenament (Pràctica Individual)

* **Acció:** Desplegar i configurar una màquina virtual des de zero utilitzant l'**OVA** de base que proporciona el client.
* **Guia de referència:** Cal seguir al peu de la lletra les tasques del document adjunt **`Projecte4-TascaSOP`** (configuració de xarxa, actualitzacions, gestió bàsica, etc.).
* **Lliurament:** **No s'ha de lliurar cap activitat ni memòria.** L'objectiu és exclusivament l'aprenentatge i la comprensió profunda del funcionament dels scripts i configuracions.

### 🎓 2. Certificació (SOP-Specialist)

* **El Repte:** Superar un **examen pràctic exigent** per validar els coneixements i assolir el rang professional de *SOP Specialist*.
* **Condicions de la Prova:**
* ⏱️ Resolució d'un cas de desplegament i auditoria en viu.
* 📝 **Material permès:** Únicament es pot disposar d'**un full manuscrit (a mà)** amb les anotacions, comandes o esquemes que consideris necessaris per a la prova.



---

## 🚀 Recomanacions per al full de suport (Manuscrit)

Atès que només es permet un full escrit a mà, assegura't de repassar i apuntar durant l'entrenament:

* [ ] Comandes de configuració de xarxa estàtica a Ubuntu Server (`netplan`).
* [ ] Gestió de paquets, repositoris i actualitzacions de seguretat (`apt`).
* [ ] Comandes clau d'auditoria de permisos (`chmod`, `chown`) i revisió de logs del sistema.

---

## 🔗 Materials de Suport

* 📄 **Document Guia:** `Projecte4-TascaSOP` (Descarregable directament des de la plataforma).
* 💿 **Imatge Base:** Fitxer OVA del servidor per a pràctiques locals.
