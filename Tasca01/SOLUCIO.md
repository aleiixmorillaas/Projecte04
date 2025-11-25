# 1. Què copiar?

**Dades més crítiques del servidor**
**Dades corporatives i documentació interna**

* Bases de dades (ERP, CRM, aplicacions internes)
* Documents compartits (gestió, comptabilitat, comercials, RRHH)

**Configuracions del servidor**

* Configuració del sistema operatiu
* Rols i serveis (Active Directory, servidors de fitxers, impressió…)
* Polítiques de seguretat i scripts

**Dades dels usuaris emmagatzemades al servidor**

* Carpetes personals redirigides (si n’hi ha)
* Correu (si el servidor gestiona email intern)

---

## Cal fer còpia dels 10 equips clients?

**Només si contenen dades crítiques que no estiguin al servidor.**
Si els usuaris guarden dades locals (Escriptori, Documents…):

* **Sí**, cal copiar almenys aquestes carpetes o forçar la redirecció al servidor.

Si totes les dades es guarden al servidor (política recomanada):

* **No és necessari** copiar els equips clients.
* Només caldria tenir una imatge base del sistema per a una reinstal·lació ràpida.

**Justificació:**
Els equips clients són fàcilment reemplaçables; el que importa és la informació.
Si les dades estan centralitzades al servidor, protegir el servidor ja garanteix la continuïtat del negoci.

---

# 2. Periodicitat i Tipus de Còpia

**Objectiu:** assegurar continuïtat + preservar versions + minimitzar espai.
Et proposo un calendari típic i molt eficient:

## Calendari setmanal de còpies

**Dilluns – Divendres (diari)**
*Còpia incremental*
Guarda només els canvis des de l'última còpia.
Ràpid i consumeix poc espai.

**Dissabte**
*Còpia diferencial*
Guarda els canvis des de l’última còpia completa.
Recuperació més ràpida que amb incrementals.

**Últim dia del mes**
*Còpia completa*
Còpia íntegra del servidor.
Serveix de punt de referència per a totes les altres còpies.

### Per què aquesta combinació?

* Completa mensual = punt segur i estable.
* Diferencial setmanal = recuperació ràpida si hi ha problema.
* Incremental diari = minimitza temps i espai d’emmagatzematge.

---

# 3. Mitjans i Ubicació (Regla 3-2-1)

## Mitjans recomanats

**NAS**
Per emmagatzematge ràpid i còpies programades dins la xarxa local.

**Cloud** (Google Cloud, AWS S3, Azure, Backblaze, Synology C2…)
Per a còpies fora del lloc (off-site). Protecció essencial contra robatoris, incendis o ransomware.

**Discos durs externs**
Per a la còpia completa mensual, guardada fora de l’empresa.

## Regla 3-2-1 aplicada

* 3 còpies de les dades
* 2 en mitjans diferents
* 1 fora de la seu (off-site)

## Implementació pràctica

**Còpia 1 (primària): NAS intern**
– Incrementals i diferencials automàtics.

**Còpia 2: Núvol (Cloud)**
– Còpia automàtica xifrada diària o setmanal.

**Còpia 3: Disc dur extern**
– Còpia completa mensual, guardada físicament fora de l’empresa
(casa del responsable, una caixa forta externa, etc.)

---

# Part 2

| **Element**         | **Proposta de la Parella**                               | **Justificació**                                                                                             |
| ------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Dades Crítiques     | Bases de Dades de Comptabilitat i Clients                | Són les que tenen requisits més estrictes: RTO < 4 h i RPO < 4 h. Canvien constantment i cal prioritzar-les. |
| Periodicitat (BD)   | Còpies incrementals cada 4 hores + còpia completa diària | Garanteix complir l’RPO de 4 hores. La còpia completa diària dona un punt de restauració sòlid.              |
| Tipus de Còpia (BD) | Sistema híbrid: Completes + Incrementals                 | Minimitza el temps i espai, mantenint la capacitat de restauració ràpida.                                    |
| Mitjà 1 (Local)     | NAS intern al CPD amb RAID 5                             | Còpia ràpida i restauració immediata. El RAID aporta tolerància a fallades i el NAS permet automatitzar.     |
| Mitjà 2 (Extern)    | Còpia en núvol                                           | Garanteix el “1 off-site” de l’esquema 3-2-1. Protegeix contra robatori, incendi o desastre físic.           |

---

## Explicació breu del sistema 3-2-1 implementat

**3 còpies:**

* Dades originals al servidor Ubuntu
* Còpia local al NAS
* Còpia externa al núvol

**2 tipus de mitjà:**

* Emmagatzematge local (NAS RAID)
* Emmagatzematge al núvol

**1 còpia fora de la ubicació física:**

* La còpia al núvol xifrada
