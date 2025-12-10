# Projecte04: Servidor NFS

## El Cas Client:  DevOptimize Solutions

El nostre client, `DevOptimize Solutions`, és una petita startup de desenvolupament de programari que treballa exclusivament amb Linux. Tenen un problema crític: el seu codi font i els seus actius (documents de disseny, scripts) estan descontrolats. Cada desenvolupador té còpies locals, cosa que provoca errors de versió constants i una pèrdua d'eficiència brutal.
Ens han contractat per implementar un servidor de fitxers centralitzat. Atès que tot l'entorn és Linux, la solució nativa, més ràpida i eficient del sector és NFS (Network File System).
El client ha insistit en que treballa sense un entorn d’autenticació centralitzada i que, de moment, no té previst fer aquest pas.

Per mostrar al client com quedarà la solució proposada a partir de les seves demandes i poder mostrar també les seves limitacions, se t’encarrega fer una demostració del sistema.

Crearàs un servidor NFS (NFSv3) i un client Linux que consumeixi els recursos compartits. Hauràs de crear usuaris i grups per simular l'entorn del client i demostrar el control d'accés utilitzant les opcions d'exportació (/etc/exports) i els permisos del sistema de fitxers (chmod, chown).

Aquí tens el text reescrit amb un estil més clar, coherent i formal **sense modificar cap de les comandes**, tal com has demanat:

---

Per iniciar aquesta guia necessitarem dues màquines virtuals: un **Ubuntu Server** i un **Zorin OS**, que utilitzarem per simular el client.
Totes dues màquines han de disposar de **dues interfícies de xarxa**, una configurada com a **NAT** i l’altra com a **host-only**.

Quan ja tinguem les màquines instal·lades, començarem configurant el servidor.
El primer pas serà actualitzar els paquets del sistema amb la comanda:

```bash
sudo apt update && sudo apt upgrade -y 
```

Un cop actualitzat, passarem a crear l’estructura de carpetes, els grups i els usuaris necessaris.
En primer lloc, crearem els grups indicats: **devs** i **admin**. Per fer-ho utilitzarem:

```bash
groupadd devs
```

```bash
groupadd admin
```

Podem verificar que els grups s’han creat correctament consultant l’arxiu */etc/group* amb la comanda:

```bash
grep devs /etc/group
```

```bash
grep admin /etc/group
```

On haurem de veure els grups recentment creats.

![imatge dels grups](img/1.png)

A continuació crearem els usuaris.
Primer generarem **dev01**, assignant-lo al grup *devs*:

```bash
useradd -G devs -m -s /bin/bash dev01
```

Després farem el mateix amb l’usuari **admin01**, associant-lo al grup *admin*:

```bash
useradd -G admin -m -s /bin/bash admin01
```

Podem comprovar la correcta creació dels usuaris amb:

```bash
grep dev01 /etc/passwd
```

```bash
grep admin01 /etc/passwd
```

![imatge dels usuaris](img/2.png)

Un cop tinguem usuaris i grups, procedirem a crear els directoris que utilitzarà el servei.
Primer, el directori per als projectes de desenvolupament, situat a */srv/nfs/dev_projects*:

```bash
mkdir /srv/nfs/dev_projects -p
```

Després, el directori per a les eines d’administració:

```bash
mkdir /srv/nfs/admin_tools
```

![Creació de carpetas](img/3.png)

Ara configurarem els permisos d’aquests directoris.
Primer n’assignarem la propietat amb **chown**:

```bash
chown root:devs /srv/nfs/dev_projects
```

```bash
chown root:admin /srv/nfs/admin_tools
```

Tot seguit aplicarem els permisos corresponents amb **chmod**:

```bash
chmod 770 /srv/nfs/dev_projects
```

```bash
chmod 770 /srv/nfs/admin_tools
```

Podem comprovar-ho amb:

```bash
ls -l /srv/nfs
```

![Permisos de la carpeta](img/4.png)

Abans de continuar amb la configuració del servidor, cal replicar la creació dels grups i usuaris a la màquina client (Zorin).
Ho farem mitjançant l’eina gràfica **“Users and Groups”**.

![aplicació](img/5.png)

Després, igual que abans, podem validar la creació utilitzant *grep*:

![grups](img/6.png)

![usuaris](img/7.png)

És important verificar que els **UID** i **GID** coincideixen exactament entre el servidor i el client, ja que NFS depèn d’aquests identificadors.

Quan tot coincideixi, ja podrem instal·lar el servei NFS al servidor amb:

```bash
apt install nfs-kernel-server -y
```

Per confirmar que la instal·lació és correcta, podem consultar l’estat del servei:

```bash
systemctl status nfs-kernel-server
```
