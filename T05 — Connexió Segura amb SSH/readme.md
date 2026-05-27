# 🚀 T05: Accés Remot — Guia Interna de Connexió via SSH (PoC)

Benvingut a la **Base de Coneixement d'EverPia**. Com a consultors tecnològics, la gestió remota segura és el nostre pa de cada dia. Aquest document serveix com a **Prova de Concepte (PoC)** i guia d'aterratge per a nous tècnics i becaris de l'equip.

Aquí aprendràs a administrar els servidors de la consultora i dels nostres clients (com *Garriga & Associats*) de forma 100% xifrada i eficient.

---

## 📌 Objectius de la PoC

* 🛠️ **Establir connexions segures** des de qualsevol entorn de treball de l'empresa.
* 🐧 **Clients Linux:** Administració nativa mitjançant la terminal.
* 🪟 **Clients Windows:** Ús de PowerShell i la Terminal moderna.
* 🔑 **Seguretat Avançada:** Configuració de claus públiques/privades per eliminar l'ús de contrasenyes vulnerables.

---

## 💻 1. Connexió des de Clients Linux (Terminal Nativa)

Linux és el nostre entorn natiu preferit per a l'administració de sistemes. Segueix aquests passos per connectar-te:

### Pas A: Connexió bàsica per contrasenya

Obre la teva terminal i executa la comanda bàsica d'accés:

```bash
ssh usuari@ip_del_servidor

```

> ⚠️ **Nota de seguretat:** La primera vegada que et connectis, la terminal et demanarà acceptar la lda de la clau de l'host (*ECDSA key fingerprint*). Escriu `yes` per continuar.

### Pas B: Configuració de Clau Pública/Privada (Sense contrasenya)

Per automatitzar i protegir l'accés als servidors d'EverPia, mai fem servir contrasenyes en producció.

1. **Generar el parell de claus** a la teva màquina local:
```bash
ssh-keygen -t ed25519 -C "el_teu_correu@everpia.com"

```



```
   *(Prem `Enter` per desar-ho a la ruta per defecte i afegeix una contrasenya de pas o passphrase si vols doble seguretat).*

2. **Copiar la clau pública al servidor** del client:
   ```bash
   ssh-copy-id usuari@ip_del_servidor

```

3. **Iniciar sessió directament:** Ara ja pots entrar de forma segura sense que et demani la contrasenya de l'usuari.

---

## 🪟 2. Connexió des de Clients Windows (PowerShell / Terminal)

A les estacions de treball Windows utilitzem el client OpenSSH natiu ja integrat a les versions modernes del sistema.

### Pas A: Verificar el servei OpenSSH

Obre **PowerShell** com a Administrador i comprova que el client SSH està actiu:

```powershell
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH.Client*'

```

### Pas B: Executar la connexió

Pots fer anar exactament la mateixa sintaxi que a Linux des de la teva terminal de Windows:

```powershell
ssh usuari@ip_del_servidor

```

### Pas C: Creació de claus a Windows

Si estàs a Windows i necessites generar les claus per no usar contrasenyes:

1. Executa `ssh-keygen -t ed25519` a la PowerShell.
2. Per pujar la clau (ja que Windows no té `ssh-copy-id` de manera nativa), pots utilitzar aquesta comanda:
```powershell
cat ~/.ssh/id_ed25519.pub | ssh usuari@ip_del_servidor "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

```



```

---

## 🔍 3. Activitats de Verificació (Pràctica SSH del Moodle)

Com a part de la PoC, assegura't de documentar amb captures de pantalla els següents punts extrets de la pràctica de la UD4.AA2:

- [ ] **Captura 1:** Ping inicial entre les teves màquines virtuals (Client 🔄 Servidor).
- [ ] **Captura 2:** Connexió SSH amb èxit de Linux a Servidor demanant contrasenya.
- [ ] **Captura 3:** Generació de claus i contingut del fitxer `authorized_keys` al servidor.
- [ ] **Captura 4:** Connexió final automatitzada (sense contrasenya) des de Windows/Linux.

---

## 🛠️ Comandes ràpides de referència (Xat de l'Administrador)

| Acció | Comanda | Propòsit |
| :--- | :--- | :--- |
| **Sortir** | `exit` | Tanca la sessió SSH actual de forma segura. |
| **Copiar fitxers** | `scp fitxer.txt usuari@ip:/ruta/` | Transferència de fitxers segura a través d'SSH. |
| **Editar configuració** | `sudo nano /etc/ssh/sshd_config` | Fitxer del servidor (per canviar el port 22 o deshabilitar l'accés root). |

---
🌟 *Aquesta documentació és propietat intel·lectual de l'equip d'infraestructura d'EverPia. Fes-ne un ús responsable i ajuda als nous companys a mantenir els nostres sistemes segurs.*

```
