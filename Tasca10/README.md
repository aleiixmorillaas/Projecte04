# **T10: Servidor d’Impressió Linux — CUPS**

*Tasca individual*

## **Breu Descripció**

---

## **Introducció**

Molt bé, equip.

A EverPia, busquem constantment **optimitzar els recursos dels clients** per reduir costos i simplificar la gestió.

Un dels punts més caòtics en qualsevol oficina és la **gestió d’impressores**:

* Drivers incompatibles
* Tòner descontrolat
* Equips que no saben a quina impressora enviar la feina

La solució professional: **Servidor d’Impressió Centralitzat**.

---

## **Cas del Client: DevOptimize Solutions**

* Objectiu: centralitzar la impressió a tots els departaments.
* Entorn: **clients Linux (Zorin OS)** i **servidors Ubuntu Server**.

El client vol una **Prova de Concepte (PoC)** abans d’invertir en impressores de xarxa.

---

## **Prova de Concepte (PoC)**

### **Objectiu**

* Configurar un servidor Linux que gestioni una impressora i la comparteixi amb clients Zorin.
* Simularem la impressora amb **cups-pdf**, que imprimeix documents en fitxers PDF al servidor.

---

## **Escenari de Treball**

* **Màquina 1 (Servidor):** Ubuntu Server

  * Interfície NAT
  * Interfície Host-Only

* **Màquina 2 (Client):** Zorin OS (Desktop)

  * Mateixa configuració de xarxa que el servidor

> Nota: S’utilitzen les mateixes màquines que en la PoC de NFS.

---

## **Passos de la PoC**

1. **Instal·lació de CUPS al servidor**

   ```bash
   sudo apt update
   sudo apt install cups
   ```
2. **Instal·lació de la impressora virtual cups-pdf**

   ```bash
   sudo apt install printer-driver-cups-pdf
   ```
3. **Configuració de l’administració de CUPS**

   * Permetre que CUPS escolti **per totes les interfícies**.
   * Edita `/etc/cups/cupsd.conf` i ajusta `Listen` i permisos.
4. **Compartir la impressora via web**

   * Accedeix a l’administració web: `http://localhost:631`
   * Afegir i compartir la impressora cups-pdf.
5. **Configurar el client Zorin**

   * Afegir la impressora compartida a través de la xarxa.
6. **Fer proves d’impressió**

   * Enviar diversos documents des del client.
7. **Comprovació al servidor**

   * Verificar que els fitxers PDF corresponents es generen correctament al directori designat (`/var/spool/cups-pdf/USERNAME`).

> Documentar totes les comandes, opcions i captures de pantalla per demostrar el correcte funcionament.

---

## **Materials i Recursos de Suport**

### **1. Material propi**

* UD5. AA1. CUPS (disponible al Moodle del mòdul de Sistemes Operatius en Xarxa)

### **2. Recursos externs**

* **Vídeo tutorial:** Instalació de servidor CUPS
  J.B. Alex Mantich (2024, 15 febrer) — YouTube
  [https://www.youtube.com/watch?v=FNwSTrOSgZQ](https://www.youtube.com/watch?v=FNwSTrOSgZQ)

* **Guia instal·lació CUPS Ubuntu 24.04 LTS**
  R00t/2025, Idroot
  [https://idroot.us/install-cups-print-server-ubuntu-24-04/](https://idroot.us/install-cups-print-server-ubuntu-24-04/)

* **Documentació Ubuntu Server** (NFS, útil com a referència de xarxa)
  [https://documentation.ubuntu.com/server/how-to/networking/install-nfs/](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)
