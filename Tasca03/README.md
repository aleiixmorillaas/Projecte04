# **T03: Pla de Recuperació davant Desastres — Imatges del Sistema**

## **Breu Descripció**

## **Introducció al Cas**

Recordeu el cas del portàtil al qual no es podia accedir? En aquella situació, tant la recuperació de l’accés com la posterior fortificació del sistema van deixar el client força impressionat.
Ara, el client us vol incloure en el seu **nou encàrrec**: l’elaboració d’un **Pla de Contingència i Continuïtat del Negoci**.

Dins d’aquest pla, cal posar en marxa el **Pla de Recuperació davant Desastres (DRP)**, que inclou tots els processos necessaris per restaurar dades, hardware i software crític després d’un esdeveniment catastròfic, amb l’objectiu de recuperar l’activitat normal tan aviat com sigui possible.

Un dels punts clau és garantir que els treballadors disposin **ràpidament dels seus equips de treball** en cas de robatori, avaria o altres incidents. Per això, no és viable la solució clàssica de reinstal·lar el sistema, configurar-lo i reinstal·lar aplicacions; és necessari un **sistema d’imatges de restauració**.

Els equips del client utilitzen **Zorin OS 18** amb un conjunt d’aplicacions i configuracions predefinides.

---

# **Fase 1: Anàlisi i Justificació de la Solució Tècnica**

En aquesta fase cal investigar diverses eines (tant comercials com de comunitat) que permetin:

* Crear una imatge completa del disc d’un equip.
* Restaurar-la posteriorment amb totes les configuracions, aplicacions i dades intactes.

Hi ha moltes solucions al mercat. Cal elaborar una **comparativa** entre:

* **2 eines comercials**
* **2 eines de comunitat**

La comparativa ha d’incloure:

* Característiques principals
* Preu
* Avantatges i inconvenients

> ⚠️ **Important:** Ha de ser una *comparativa real*, no un recull de textos copiats de les webs oficials.

### **Proposta final**

Cal indicar quina solució proposeu per al client, amb una justificació basada en:

* cost
* facilitat d’ús
* manteniment
* compatibilitat amb Zorin OS
* automatització
* seguretat

---

# **Fase 2: Guia d’Ús Tècnica (Manual Operatiu)**

Usant la màquina proporcionada pel client (simulada amb una **OVA**), cal realitzar els següents processos:

### **1. Crear una imatge completa del sistema**

Capturar tot el disc incloent:

* sistema operatiu
* configuracions
* aplicacions
* dades

### **2. Restaurar la imatge**

Restaurar-la sobre un equip net:

* Mateixa configuració tècnica (RAM, CPU, disc, xarxa)
* Sense cap sistema operatiu instal·lat

Aquesta restauració servirà com a **prova de concepte**.

---

# **Guia Tècnica**

S’ha d’elaborar una guia completa perquè el personal de manteniment pugui:

* crear imatges del sistema
* restaurar-les

> ✔️ Documentar amb captures útils i passos detallats.

Encara que la solució final dependrà de si el client accepta la vostra proposta, en aquesta prova de concepte **s’utilitzarà Rescuezilla** per fer la guia.

> 📌 *Aquesta tasca és individual.*

---

# **Materials i Links de Suport**

* **INCIBE – ¿Ya tienes tu Plan de Recuperación ante Desastres?**
  [https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres](https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres)

* **Pàgina oficial de Rescuezilla**
  *(Enllaç disponible mitjançant cerca al web del projecte.)*
