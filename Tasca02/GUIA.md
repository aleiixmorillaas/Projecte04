Perfecte, ara entès al 100% 👌
A continuació tens **el document en Markdown** però **indicant explícitament on va cada imatge**, numerada i explicada, perquè quedi clar **quina captura correspon a cada pas** (ideal per memòria, pràctica o defensa).

---

# Part 1: Còpia de seguretat dels equips clients Windows

## 1. Configuració del segon disc

Per començar, el primer pas serà disposar d’una màquina client Windows amb un disc principal on estigui instal·lat el sistema operatiu i un segon disc de 10 GB que utilitzarem per a la còpia de seguretat.

**Imatge 1:** Configuració del segon disc a la màquina virtual.
![configuració del segon disc](img/1.png)

---

## 2. Inicialització del disc

Un cop afegit el disc secundari, iniciarem la màquina i obrirem l’administrador de discs per inicialitzar-lo.

**Imatge 2:** Administrador de discs de Windows mostrant el disc sense inicialitzar.
![administrador de disc](img/2.png)

---

## 3. Creació del volum simple

A continuació, crearem un volum simple fent clic dret sobre el disc i seleccionant l’opció **“Nuevo volumen simple”**.

**Imatge 3:** Assistents de creació del volum simple finalitzat correctament.
![Crear volum simple](img/3.png)

---

## 4. Descàrrega de Duplicati

El següent pas serà descarregar el programari Duplicati des del seu lloc web oficial.

**Imatge 4:** Pàgina de descàrrega de Duplicati amb la versió per a Windows.
![Crear volum simple](img/4.png)

---

## 5. Instal·lació de Duplicati

Executarem l’arxiu `.exe` descarregat i seguirem l’assistent d’instal·lació fins a completar el procés.

**Imatge 5:** Procés d’instal·lació de Duplicati en Windows.
![Instalació duplicati](img/5.png)

---

## 6. Configuració inicial de Duplicati

Un cop instal·lat, s’obrirà una pestanya al navegador on configurarem la contrasenya d’accés a Duplicati.

**Imatge 6:** Pantalla inicial de Duplicati demanant la contrasenya.
![duplicati](img/6.png)

---

## 7. Creació de documents de prova

Abans de fer la còpia, crearem alguns documents de prova per verificar el funcionament del backup.

**Imatge 8:** Documents de prova creats a l’equip client.
![Creació de documents](img/8.png)

---

## 8. Creació d’una nova còpia de seguretat

A Duplicati, seleccionarem **Add backup** i **Add new backup** per començar la configuració de la còpia.

**Imatge 7:** Pantalla de configuració inicial d’un nou backup a Duplicati.
![duplicati](img/7.png)

---

## 9. Selecció de la ubicació de la còpia local

Escollirem el disc secundari com a destinació de la còpia de seguretat.

**Imatge 9:** Selecció del disc secundari com a ubicació del backup.
![Escollir lloc](img/9.png)

---

## 10. Selecció dels fitxers a copiar

Seleccionarem les carpetes i fitxers que volem incloure a la còpia de seguretat.

**Imatge 10:** Selecció dels documents a incloure en el backup.
![Escollir documents](img/10.png)

---

## 11. Configuració de la freqüència del backup

Definirem cada quant temps es realitzarà la còpia. En aquest cas, cada 1 hora.

**Imatge 11:** Configuració de la planificació del backup.
![Escollir temps](img/11.png)

---

## 12. Opcions finals del backup

Configurarem les opcions finals i finalitzarem la creació de la còpia.

**Imatge 12:** Opcions finals de configuració del backup.
![opcions](img/12.png)

---

## 13. Configuració del backup al núvol (Google Drive)

Crearem una nova còpia de seguretat, però aquesta vegada al núvol utilitzant Google Drive, vinculant el compte amb **AuthID**.

**Imatge 13:** Vinculació del compte de Google Drive amb Duplicati.
![googledrive](img/13.png)

---

## 14. Programació del backup al núvol

Configurarem l’horari del backup perquè s’executi cada dia a les 18:00.

**Imatge 14:** Configuració de l’horari del backup al núvol.
![Horari](img/14.png)

---

## 15. Còpies creades correctament

Un cop finalitzat el procés, comprovarem que les dues còpies s’han creat correctament.

**Imatge 15:** Llista de còpies de seguretat creades a Duplicati.
![copies creades](img/15.png)

---

## 16. Eliminació dels documents de prova

Esborrarem els documents de prova per comprovar la restauració.

**Imatge 16:** Carpeta de documents sense els fitxers de prova.
![Carpeta documents](img/16.png)

---

## 17. Inici del procés de restauració

Accedirem a **Restores** i iniciarem el procés de restauració seleccionant la còpia corresponent.

**Imatge 17:** Selecció de la còpia a restaurar.
![Escollir copia](img/17.png)

---

## 18. Selecció dels fitxers a restaurar

Escollirem els fitxers i carpetes que volem recuperar.

**Imatge 18:** Selecció dels documents a restaurar.
![Escollir documents](img/18.png)

---

## 19. Restauració completada

Finalitzarem l’assistent i comprovarem que la restauració s’ha realitzat correctament.

**Imatge 19:** Restauració finalitzada correctament.
![Restauració feta](img/19.png)

**Imatge 20:** Documents restaurats correctament a la carpeta original.
![Restauració feta](img/20.png)
