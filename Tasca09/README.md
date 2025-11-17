# **T09: Servidor de Fitxers Linux — NFS**

*Tasca individual*

## **Breu Descripció**

---

## **Introducció**

Molt bé, equip de consultors júniors.

En aquest punt del projecte ens trobem amb un requisit tècnic molt habitual entre els nostres clients: la **centralització de dades en entorns Linux**.

---

## **El Cas del Client: DevOptimize Solutions**

El nostre client és una petita startup de desenvolupament de programari que treballa **exclusivament amb Linux**.

Actualment tenen un problema greu:

* El codi font i els actius (documents, scripts, dissenys) estan distribuïts caòticament entre els equips locals.
* Cada desenvolupador té la seva pròpia còpia → **errors de versió**, fitxers inconsistents i molta pèrdua de temps.

Ens han contractat per implementar un **servidor de fitxers centralitzat**.

Com que tot l’entorn és Linux, la solució més adequada és:

> **NFS (Network File System)** — l’opció estàndard, nativa i més eficient per compartir dades entre equips Linux.

---

## **Requisits importants del client**

* No utilitzen **cap entorn d’autenticació centralitzada** (no LDAP, no AD).
* No tenen previst implementar-ne un a curt termini.
* L’entorn de treball actual està basat exclusivament en **usuaris i grups locals**.

Per això és important que la demostració reflecteixi:

* Limitacions del sistema sense autenticació centralitzada.
* Com el control d’accés depèn dels UID/GID i permisos del sistema de fitxers.

---

## **La Teva Missió**

Per presentar al client una **prova de concepte funcional**, hauràs de construir un entorn format per:

### **1️⃣ Un servidor NFS (NFSv3)**

Incloent:

* Instal·lació i configuració del servei.
* Creació de directoris compartits.
* Definició de permisos i propietaris.
* Configuració d’exportacions a `/etc/exports`.

### **2️⃣ Un client Linux**

Que:

* Es connecti al servidor NFS.
* Munti els recursos compartits.
* Demostri lectura/escriptura segons permisos.

### **3️⃣ Simulació de l’entorn de treball real**

Creant:

* **Usuaris locals** equivalents als desenvolupadors.
* **Grups locals** per gestionar projectes o departaments.
* Proves de control d’accés:

  * permisos UNIX (`chmod`)
  * propietaris (`chown`)
  * opcions d’exportació NFS (`rw`, `ro`, `sync`, `no_root_squash`, etc.)

L’objectiu és mostrar al client:

✔ com centralitzar els fitxers,
✔ com controlar-ne els accessos,
✔ i també les **limitacions** de no tenir un sistema d’autenticació centralitzat (especialment la dependència de UID/GID iguals).

---

## **Repositori Oficial de la Tasca**

📌 **[https://github.com/SMX2n/Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS)**

Aquest repositori explica exactament què has de fer i quins passos cal seguir per a la pràctica.

[

---

## **Materials i Recursos de Suport**

### **1. Material propi del centre**

* *UD5. AA1. NFS* (disponible al Moodle del mòdul de Sistemes Operatius en Xarxa).

### **2. Tutorials externs recomanats**

* **Instal·lació del servidor NFS (Ubuntu 20.04)**
  Ruiz, P. (2021, novembre 22)
  *SomeBooks.es*

* **Instal·lació del client NFS (Ubuntu 20.04)**
  Ruiz, P. (2021, desembre 2)
  *SomeBooks.es*

* **Documentació oficial d’Ubuntu Server — NFS**
  *Ubuntu Documentation*
