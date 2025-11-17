# **T01: DRP — Còpies de Seguretat · Estudi del Cas del Client (Treball Cooperatiu)**

## **Breu Descripció**

### **Introducció**

La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. A continuació, haureu de treballar els aspectes del tema mitjançant una dinàmica cooperativa.

---

## **Presentació del Cas Client**

**"Muntatges i Serveis Tècnics SL"** és una petita empresa dedicada a la instal·lació i manteniment d'equips industrials.

### **Infraestructura Tècnica**

* **Servidor de Fitxers (Ubuntu Server)**
  Conté tota la documentació crítica:

  * **Documents de Projectes:** Plànols, especificacions tècniques (300 GB, creixement moderat).
  * **Bases de Dades (Comptabilitat i Clients):** Crítiques i d'ús diari (20 GB, canvi constant).
  * **Carpetes Personals dels Usuaris:** Per a la feina diària (100 GB).

* **10 Equips Clients (Windows 10/11)**
  Treballen principalment amb fitxers del servidor, però alguns tècnics guarden temporalment informes i altres arxius importants a *Documents*.

* **Connexió a Internet:** Fibra òptica de **600 Mbps simètrica**.

### **Requisits de Recuperació**

* **RTO (Temps de Recuperació):** Les dades de Comptabilitat/Clients han d'estar disponibles en **menys de 4 hores**.
* **RPO (Pèrdua de Dades Admesa):**

  * Resta de dades: pèrdua màxima de **24 hores**.
  * Comptabilitat/Clients: màxim **4 hores de treball**.
* **Retenció:** Cal guardar les dades amb un historial d’**almenys 1 mes**.

---

# **Fase 1: Treball Individual**

Respon de manera individual basant-te en el cas pràctic:

1. **Què copiar? (Priorització)**
   Quines són les dades més crítiques del servidor?
   Cal fer còpia dels 10 equips clients? Justifica-ho.

2. **Periodicitat i Tipus de Còpia**
   Proposa un calendari bàsic semanal (Diari / Setmanal / Mensual).
   Quin tipus de còpia aplicaràs? (Completa, Diferencial, Incremental).

3. **Mitjans i Ubicació**
   Quin tipus de mitjà utilitzaries? (Discs durs externs, NAS, Cloud, Cintes).
   On s’ha de guardar físicament la còpia més recent? (Regla **3-2-1**).

---

# **Fase 2: Treball per Parelles**

### **1. Discussió i Consens**

Posar en comú les respostes individuals (Fase 1).

### **2. Elaboració d'una Proposta Unificada**

Dissenyeu el vostre propi **Esquema 3-2-1**:

* **3** còpies
* **2** mitjans diferents
* **1** fora del lloc

| **Element**             | **Proposta de la Parella** | **Justificació** |
| ----------------------- | -------------------------- | ---------------- |
| **Dades Crítiques**     |                            |                  |
| **Periodicitat (BD)**   |                            |                  |
| **Tipus de Còpia (BD)** |                            |                  |
| **Mitjà 1 (Local)**     |                            |                  |
| **Mitjà 2 (Extern)**    |                            |                  |

---

# **Fase 3: Treball en Grup**

### **1. Debat i Selecció**

Cada parella presenta el seu esquema. El grup valora pros i contres considerant:

* cost
* temps de recuperació
* seguretat
* simplicitat

### **2. Disseny de la Política Final**

El grup redacta la **Política de Còpies de Seguretat Definitiva** per a l’empresa *"Muntatges i Serveis Tècnics SL"*.

---

# **Document Final (Fase 3)**

El document final ha d’incloure:

---

## **1) Dades Objecte de Còpia**

Especificar:

* Quines dades es copien
* Amb quina freqüència
* Diferenciant: **Servidor / Clients** i **crítiques / no crítiques**

---

## **2) Cronograma Setmanal Detallat**

| **Dia**  | **Dades** | **Tipus de Còpia** | **Mitjà** |
| -------- | --------- | ------------------ | --------- |
| Dilluns  |           |                    |           |
| Dimarts  |           |                    |           |
| …        |           |                    |           |
| Diumenge |           |                    |           |

---

## **3) Elecció de Mitjans i Ubicació (Regla 3-2-1)**

* **Mitjà 1 (Local):**
  (Disc dur USB, NAS, etc.)

* **Mitjà 2 (Extern):**
  (Cloud, LTO...).
  Proveïdor (Azure, Google Cloud, servei local...).

* **Ubicació Fora de Lloc:**
  On es guarda la còpia externa (física o lògica).
  Responsable de la seva gestió.

---

## **4) Estratègia de Recuperació (RTO/RPO)**

Explicar com es garanteix que les dades de Comptabilitat/Clients compleixen:

* **RPO ≤ 4 hores**
* **RTO ≤ 4 hores**

---

# **Materials i Links de Suport**

* Moodle 0226 Seguretat Informàtica — RA2.AA3 Còpies
* **INCIBE:** *Copias de seguridad. Una guía de aproximación para el empresario.*
* **Xataka:** *Backup 3-2-1, el método definitivo para mantener a salvo tus datos.*
  *(YouTube, 2017)*
  [https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8](https://youtu.be/PM_M4Iz6I4o?si=F7DRyDDTZE3hjWn8)
