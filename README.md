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

## qbittorrent installieren
``` bash
sudo apt install qbittorrent-nox
sudo useradd -r -m qbittorrent
sudo usermod -a -G qbittorrent pi
# Daemon erstellen
sudo nano /etc/systemd/system/qbittorrent.service
# Folgende Zeilen in das File einfügen
[Unit]
Description=qBittorrent
After=network.target

[Service]
Type=forking
User=qbittorrent
Group=qbittorrent
UMask=002
ExecStart=/usr/bin/qbittorrent-nox -d --webui-port=8080
Restart=on-failure

[Install]
WantedBy=multi-user.target

# Service Testen
sudo systemctl start qbittorrent
sudo systemctl status qbittorrent

# Autostart aktivieren
sudo systemctl enable qbittorrent
```

Auf die Website verbinden: http://[IP VOM RASPY]:8080
