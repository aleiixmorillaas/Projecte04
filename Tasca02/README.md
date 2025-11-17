# **T02: DPR — Còpies de Seguretat · Cas Pràctic**

## **Breu Descripció**

## **Introducció al Cas**

En la tasca anterior heu dissenyat una política de còpies de seguretat per al client **"Muntatges i Serveis Tècnics SL"**.
Ara toca **passar a l’acció**: el client demana una sèrie de **guies tècniques amb proves de concepte** perquè el seu personal pugui implantar el pla de còpies de seguretat.

---

# **Part 1: Còpia de Seguretat dels Equips Clients Windows**

Encara que el DRP original no contemplava fer còpies dels equips clients, el director de l’empresa guarda informació sensible localment i cal fer-ne còpia.

Es defineix una política **3-2-1**:

* **3 còpies**
* **2 mitjans diferents** (disc secundari + cloud)
* **1 còpia fora de lloc** (Google Drive)

S’utilitzarà **Duplicati** com a eina de còpies.

### **Prova de concepte**

Haureu de crear:

* Una màquina virtual **Windows 11**
* **Dos discos**

  * Disc 1: Sistema operatiu
  * Disc 2: 10 GB (emmagatzematge de còpies)
* Un compte de Google Drive (no el del centre; podeu crear-ne un específic)

### **Requisits de còpia**

* **Cada hora** → còpia al disc secundari
* **A les 18:00** → còpia a Google Drive

### **Tasques a documentar**

1. Instal·lació de **Duplicati**
2. Configuració dels **plans de còpies**
3. Observació del funcionament

   * Afegiu arxius al perfil de l’usuari, especialment a *Documents*
4. **Esborrar** el contingut de *Documents*
5. Restauració des del **disc secundari**
6. Restauració des de la còpia del **cloud (Google Drive)**

---

# **Part 2: Còpia de Seguretat al Servidor Linux**

El responsable proposa **Duplicity**, que permet fer còpies locals i remotes.
Combinat amb **cron**, es podran crear polítiques automatitzades.

La guia tècnica es farà sobre una màquina virtual **Ubuntu Server** amb un segon disc de **10 GB** per simular una unitat de backup.

---

## **Guia i Prova de Concepte**

### **1. Preparació del disc de backup**

1. Inicialitza el disc i formata’l en **XFS**.
2. Crea la carpeta `/media/backup`.
3. Munta manualment la unitat (simula un dispositiu extern).

### **2. Instal·lació**

* Instal·la **Duplicity**.

### **3. Preparació de dades**

1. Crea **dos usuaris nous** amb carpeta personal.
2. Crea **4 arxius de 10 MB** a `/home/<usuari>`.

### **4. Primera còpia**

* Fes una còpia de seguretat de la carpeta **/home**.

### **5. Restauració**

* Esborra els arxius i comprova la recuperació amb un **restore**.

### **6. Còpia incremental**

1. Afegeix un fitxer **nou de 4 MB**.
2. Fes una nova còpia.
3. Observa com ara Duplicity genera una **còpia incremental**.

### **7. Desmuntatge**

* Desmunta la unitat de backup.

---

# **Automatització amb Scripts i Cron**

La unitat de backup **ha d’estar desmuntada per defecte**, per motius de seguretat.
Cada script ha de:

* muntar la unitat
* fer la còpia
* desmuntar la unitat

---

## **7. Script `fullbackup.sh`**

* Realitza una còpia **completa** de `/home`
* Utilitza la variable d’entorn:

  ```bash
  export PASSPHRASE=contrasenya
  ```
* Dona permisos d’execució a l’script.

## **8. Programació amb `cron`**

Com a root:

* Executar **diumenges a les 23:00**

  ```
  0 23 * * 0 /ruta/fullbackup.sh
  ```

---

## **9. Script `incrementalbackup.sh`**

* Realitza còpies **incrementals** de la carpeta `/home`
* Inclou la variable `PASSPHRASE` igual que abans
* Dona permisos d’execució

## **10. `cron` incremental**

Com a root:

* Executar **de dilluns a dissabte a les 23:00**

  ```
  0 23 * * 1-6 /ruta/incrementalbackup.sh
  ```

---

# **Materials i Links de Suport**

* **Duplicati:**
  [https://duplicati.com/](https://duplicati.com/)

* **Creació d’arxius amb fsutil (Windows) – WayToIT (2015):**
  [https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/](https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/)

* **Creació d’arxius de prova a Linux – WayToIT (2015):**
  [https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/](https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/)

* **Duplicity – Man Page:**
  [http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html](http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html)

* **Programar tasques amb cron:**
  [https://geekytheory.com/programar-tareas-en-linux-usando-crontab](https://geekytheory.com/programar-tareas-en-linux-usando-crontab)
