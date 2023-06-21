# M239-Raspberry
## Vorbereitungen
Raspberry Pi Imager herunterladen: https://www.raspberrypi.com/software/
SD Karte mit dem Raspberry Pi OS beschreiben
  - 32-Bit Betriebsystem
  - Unter den Einstellungen SSH & Benutzer konfigurieren

## RaspAP installieren
``` bash
sudo apt-get update
sudo apt-get full-upgrade
sudo reboot
# WLAN Localication Konfigurieren
sudo raspi-config (5/L4/CH)
# RaspAP Quick installer
curl -sL https://install.raspap.com | bash
```
