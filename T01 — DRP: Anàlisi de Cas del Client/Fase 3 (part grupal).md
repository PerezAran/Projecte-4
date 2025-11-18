# DRP: Còpies de seguretat (GRUP)

## Introducció
Aquest document descriu l'estratègia de còpia de seguretat i recuperació de dades del nostre entorn IT, amb l'objectiu de garantir la disponibilitat i integritat de la informació crítica. S'han identificat les dades a protegir, la freqüència de les còpies, els mitjans i ubicacions utilitzats, així com els procediments de recuperació davant incidències. La metodologia segueix la Regla 3-2-1 i assegura que les dades de comptabilitat i clients compleixin els requisits de RPO i RTO de 4 hores, garantint així la continuïtat del negoci davant qualsevol eventualitat.

## Índex
1. Introducció
2. Dades Objectes de còpia
3. Cronograma Setmanal detallat
4. Elecció de mitjans i ubicació
5. Estratègies de recuperació
6. Conclusió

## Dades Objectes de còpia
Hem volgut realitzar-ho amb tipus taula, ja que ens semblava més resumit i visible:

| Categoria | Dades | Freqüència | Notes |
|-----------|-------|-------------|-------|
| **Servidor** | Base de dades de Comptabilitat | Diària (incremental) | Crítica |
| | Base de dades de Clients | Cada 4 hores | Crítica (RPO ≤ 4h) |
| | Fitxers compartits internes | Setmanal | No crítica |
| **Clients** | Documents locals de treball | Diària | No crítica |
| | Configuracions locals | Setmanal | No crítica |
| **Altres** | Logs de sistema | Setmanal | No crítica |

Hem separat Servidor/Clients i dades Crítiques/No Crítiques per prioritzar la recuperació.

## Cronograma Setmanal detallat

| Dia | Dades | Tipus de còpia | Mitjà |
|-----|-------|----------------|-------|
| **Dilluns** | BD Comptabilitat | Incremental | NAS Local |
| | BD Clients | Incremental | NAS Local |
| **Dimarts** | Fitxers compartits | Completa | NAS Local |
| | Logs sistema | Completa | NAS Local |
| **Dimecres** | BD Comptabilitat | Incremental | NAS Local |
| | BD Clients | Incremental | NAS Local |
| **Dijous** | Fitxers compartits | Incremental | NAS Local |
| **Divendres** | BD Comptabilitat | Incremental | NAS Local |
| | BD Clients | Incremental | NAS Local |
| **Dissabte** | BD Comptabilitat | Completa | Cloud Extern |
| | BD Clients | Completa | Cloud Extern |
| **Diumenge** | Fitxers compartits | Completa | Cloud Extern |
| | Configuracions clients | Completa | Cloud Extern |

## Elecció de mitjans i ubicació

| Mitjà | Descripció | Ubicació | Responsable |
|-------|-------------|----------|-------------|
| **Mitjà 1 (Local)** | NAS amb discos RAID 5 de 10 TB | Sala de Servidors | Administrador IT local |
| **Mitjà 2 (Extern)** | Cloud Storage (Azure Blob Storage) | Data Center extern d'Azure | Administrador IT |
| **Ubicació Fora de Lloc** | Còpia externa diària al Cloud | Data Center remot | Administrador IT amb accés restringit |

**Regla 3-2-1:**
- **3 còpies**: 1 original + 2 còpies de seguretat
- **2 mitjans diferents**: NAS local i Cloud
- **1 fora de lloc**: Cloud Azure per protecció davant desastres físics

## Estratègies de recuperació

| Tipus de Dada | RPO | RTO | Estratègia |
|---------------|-----|-----|------------|
| **Comptabilitat** | 4 hores | 4 hores | - Còpies incrementals cada 4h<br>- Restauració prioritària des del NAS local<br>- Si fallida completa del servidor, recuperació des Cloud Azure |
| **Clients** | 4 hores | 4 hores | - Còpies incrementals cada 4h<br>- Restauració automatitzada amb software de backup centralitzat |
| **Fitxers compartits** | 24 hores | 24 hores | - Recuperació menys prioritària, des NAS o Cloud segons disponibilitat |

El RPO de 4 hores es garanteix amb còpies incrementals cada 4 hores.

El RTO de 4 hores s'assegura amb restauracions prioritàries locals i accés immediat a còpia Cloud en cas de desastre.

## Conclusió
L'estratègia proposada proporciona un pla de backup robust i escalable, combinant còpies locals i externes per minimitzar riscos. La definició clara de freqüències, tipus de còpia i responsabilitats assegura que les dades crítiques estiguin protegides i recuperables dins dels límits establerts. Mitjançant aquesta planificació, l'empresa disposa d'un sistema de recuperació fiable que garanteix la continuïtat operativa, redueix la possibilitat de pèrdua de dades i compleix amb els requisits de seguretat i normativa vigent.
