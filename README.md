# Activitat 1 - Administració d'Ubuntu Server 

## Alumne
**Nom:** Quico  
**Curs:** 2n SMX  
**Sistema Operatiu:** Ubuntu Server 

---

# 1. Connexió remota amb SSH

## 1.1 Obtenció de l'adreça IP

### Comanda

```bash
ip a
```

### Explicació

He executat la comanda `ip a` per visualitzar totes les interfícies de xarxa disponibles. He identificat la segona adreça IP, corresponent a la interfície Host-Only, que serà la utilitzada per connectar-me remotament des del sistema Windows.

![Imatge Ip Servidor](/ActivitatsSmx2/media/1.png)

media/ip-a.png

---

## 1.2 Connexió SSH

### Comanda

```bash
ssh usuari@adreca_ip
```

### Explicació

Des del Terminal de Windows he establert una connexió remota amb el servidor Ubuntu utilitzant el protocol SSH.

![Conexio ssh](/ActivitatsSmx2/media/)

media/ssh-login.png

---


# 2. Actualitzacions del sistema

## 2.1 Comprovació d'actualitzacions

### Comanda

```bash
sudo apt update
```

### Explicació

He actualitzat la informació dels repositoris per comprovar si existeixen paquets pendents d'actualitzar.

![Comprovacio Actualitzacio](/ActivitatsSmx2/media/3.png)


media/apt-update.png

---


## 2.2 Actualització del sistema




```bash
sudo apt upgrade 
```

### Explicació

S'han actualitzat tots els paquets instal·lats a les versions més recents disponibles als repositoris.

### Captura

![Actualitzacio](/ActivitatsSmx2/media/4.png)

---

# 3. Canvi del nom de l'equip

## 3.1 Comprovació del nom actual

### Comanda

```bash
hostnamectl
```

### Captura

![dia/hostnamectl-abans.png

---

## 3.2 Canvi del hostname

### Comanda

```bash
sudo hostnamectl set-hostname sox-qcv
```

### Explicació

He canviat el nom permanent de l'equip utilitzant les meves inicials.

### Captura

media/set-hostname.png

---

## 3.3 Configuració del nom descriptiu

### Comanda

```bash
sudo hostnamectl set-icon-name "Servidor de Quico"
```

### Explicació

He afegit una descripció identificativa per al servidor.

### Captura

![Icon con-name.png

---

## 3.4 Verificació dels canvis

### Comanda

```bash
hostnamectl
```

### Captura

![Hostnamenamectl-despres.png

---

## 3.5 Diferència entre hostname i hostnamectl

### Comanda

```bash
hostname
```

### Explicació

La comanda `hostname` només mostra el nom curt del servidor. En canvi, `hostnamectl` proporciona informació més completa sobre el sistema i la seva configuració.

### Captura

media/hostname.png

---

## 3.6 Modificació del fitxer hosts

### Comanda

```bash
sudo nano /etc/hosts
```

### Contingut

```text
127.0.0.1 localhost
127.0.1.1 sox-qcc.sox.test sox-qcc
```

### Explicació

He actualitzat el fitxer perquè el servidor resolgui correctament el nou nom configurat.

### Captura

media/etc-hosts.png

---

## 3.7 Hostname complet

### Comanda

```bash
hostname -f
```

### Explicació

La comanda mostra el nom complet de domini (FQDN), mentre que `hostname` només mostra el nom curt.

### Captura

![hostnamename-f.png

---

# 4. Canvi de contrasenya

## 4.1 Modificació de la contrasenya

### Comanda

```bash
passwd
```

### Explicació

He canviat la contrasenya de l'usuari administrador per una de nova més segura.

### Captura

media/passwd.png

---

# 5. Gestió de la instal·lació d'aplicacions

## 5.1 Cerca del paquet btop

### Comanda

```bash
apt search btop
```

### Captura

media/search-btop.png

---

## 5.2 Informació del paquet btop

### Comanda

```bash
apt show btop
```

### Explicació

He consultat informació sobre el paquet, com la versió disponible, dependències i descripció.

### Captura

![showshow-btop.png

---

## 5.3 Instal·lació de btop

### Comanda

```bash
sudo apt install btop -y
```

### Captura

![installtall-btop.png

### Verificació

```bash
btop
```

### Captura

media/btop.png

---

## 5.4 Instal·lació de lsd

### Comandes

```bash
apt search lsd
```

```bash
sudo apt install lsd -y
```

### Verificació

```bash
lsd
```

### Captura

media/lsd.png

---

## 5.5 Instal·lació d'Apache

### Comanda

```bash
sudo apt install apache2 -y
```

### Captura

![apacheache-install.png

---

### Verificació

```bash
systemctl status apache2
```

### Captura

media/apache-status.png

---

## 5.6 Desinstal·lació d'Apache

### Comanda

```bash
sudo apt purge apache2 -y
```

### Captura

media/apache-purge.png

---

## 5.7 Instal·lació de Micro

### Comanda

```bash
sudo snap install micro --classic
```

### Captura

media/micro-install.png

---

### Verificació

```bash
snap list
```

### Captura

![snap list](media/snap-

## 5.8 Actualització de Micro

### Comanda

```bash
sudo snap refresh micro
```

### Captura

![microicro-refresh.png

---

## 5.9 Eliminació de Micro

### Comanda

```bash
sudo snap remove micro
```

### Captura

media/micro-remove.png

---

# 6. Configuració d'hora, teclat i idioma

## 6.1 Zona horària actual

### Comanda

```bash
timedatectl
```

### Captura

media/timedatectl.png

---

## 6.2 Configuració de la zona horària

### Comanda

```bash
sudo timedatectl set-timezone Europe/Madrid
```

### Explicació

He configurat el servidor perquè utilitzi la zona horària d'Espanya.

### Captura

media/timezone.png

---

## 6.3 Configuració del teclat

### Comanda

```bash
sudo dpkg-reconfigure keyboard-configuration
```

### Captura

media/keyboard.png

---

## 6.4 Configuració de l'idioma

### Comandes

```bash
locale
```

```bash
sudo dpkg-reconfigure locales
```

### Captura

media/locales.png

---

# 7. Explorant arxius de configuració

## 7.1 Cerca de fitxers YAML

### Comanda

```bash
find /etc -type f -name "*.yaml"
```

### Captura

media/fin*-yaml.png

---

## 7.2 Cerca de ca*petes SSH

### Comanda

```bash
find /etc -type d -name "*ssh*"
```

### Captura

media/find-*sh.png

---

*# 7.3 Fitxers més grans de 10 MB

*## Comanda

```bash
find /var/log *type f -size +10M
```

### Captura*
media/find-logs.png

---

## 7.4 Configuració SSH sense comentaris

### Comanda

```bash
grep -vE '^\s*#|^\s*$' /etc/ssh/sshd_config
```

### Captura

media/ssh-config.png

---

# 8. Configuració de xarxa

## 8.1 Canvi a Adaptador Pont

### Explicació

He modificat la configuració de VirtualBox canviant la xarxa NAT per Adaptador Pont.

### Captura

media/bridge.png

---

## 8.2 Configuració IP fixa

### Comanda

```bash
sudo nano /etc/netplan/00-installer-config.yaml
```

### Captura

![net/netplan-config.png

---

## 8.3 Aplicació dels canvis

### Comanda

```bash
sudo netplan apply
```

### Captura

![net/netplan-apply.png

---

## 8.4 Verificació

### Comanda

```bash
ip a
```

### Captura

![ipa/ip-fixa.png

---

## 8.5 Connectivitat

### Comanda

```bash
ping 8.8.8.8
```

### Captura

![pingping.png

---

# 9. Gestió de serveis

## 9.1 Estat del servei SSH

### Comanda

```bash
systemctl status ssh
```

### Captura

media/ssh-status.png

---

## 9.2 Aturar el servei

### Comanda

```bash
sudo systemctl stop ssh
```

### Captura

media/ssh-stop.png

---

## 9.3 Iniciar el servei

### Comanda

```bash
sudo systemctl start ssh
```

### Captura

![ssh/ssh-start.png

---

# 10. Exportació de la màquina virtual

## 10.1 Tornar a DHCP

### Comanda

```bash
sudo nano /etc/netplan/00-installer-config.yaml
```

### Configuració

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: true
```

### Captura

![dha/dhcp.png

---

## 10.2 Aplicació dels canvis

### Comanda

```bash
sudo netplan apply
```

### Captura

media/dhcp-apply.png

---

## 10.3 Exportació a OVA

### Explicació

He exportat la màquina virtual des de VirtualBox utilitzant l'opció **Fitxer → Exporta servei virtualitzat**, generant un fitxer `.ova` per disposar d'una còpia completa del sistema.

### Captura

![export-ova](mediag

---

# Conclusions

Al llarg d’aquesta activitat he après a administrar un servidor Ubuntu Server mitjançant SSH, gestionar paquets, modificar la configuració del sistema, administrar serveis, configurar la xarxa i exportar una màquina virtual. Aquestes tasques m’han permès conèixer millor l’administració bàsica de sistemes GNU/Linux i adquirir experiència pràctica en la gestió d’entorns virtualitzats.
