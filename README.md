### Alternative implementation of the Bitwarden server API written in Rust and compatible with [upstream Bitwarden clients](https://bitwarden.com/download/)*, perfect for self-hosted deployment where running the official resource-heavy service might not be ideal.

📢 Note: This project was known as Bitwarden_RS and has been renamed to separate itself from the official Bitwarden server in the hopes of avoiding confusion and trademark/branding issues.

**This project is not associated with the [Bitwarden](https://bitwarden.com/) project nor Bitwarden, Inc.**

#### ⚠️**IMPORTANT**⚠️: When using this server, please report any bugs or suggestions to us directly (look at the bottom of this page for ways to get in touch), regardless of whatever clients you are using (mobile, desktop, browser...). DO NOT use the official support channels.

---


# Host your own Vaultwarden with NGINX

Diese Repository zeigt dir, wie du deinen eigenen Vaultwarden Passwort Manager Server erstellen und konfigurieren kannst. Ich nutzte hierfür Proxmox, das ganze kann aber auch mit einem RaspberryPi oder vergleichbarer Hardware gemacht werden.
Eine Ausführliche Anleitung findet du auf meinem [YouTube Kanal](https://www.youtube.com/@andreshardware).



## Features

Basically full implementation of Bitwarden API is provided including:

 * Organizations support
 * Attachments and Send
 * Vault API support
 * Serving the static files for Vault interface
 * Website icons API
 * Authenticator and U2F support
 * YubiKey and Duo support
 * Emergency Access
 

## Vorbereitungen
```sh
apt-get update && apt-get upgrade -y && apt autoremove -y
apt install curl
apt install argon2

curl -sSL https://get.docker.com | sh
apt install docker-compose -y
```

## Installation

```sh
mkdir docker
cd docker
mkdir Vaultwarden
mkdir Vaultwarden
nano docker-compose.yml
```

## Admin-Token als Hash Wert erstellen
Nach dem generieren des Admin-Token kann dieser in die Docker-Compose Datei eingefügt werden, hierbei muss vor jedem "$"- Zeichen ein weiteres "$" ergänzt werden!
```sh
# Using the Bitwarden defaults
echo -n "MySecretPassword" | argon2 "$(openssl rand -base64 32)" -e -id -k 65540 -t 3 -p 4
```


## Importieren der docker-compose.yml Datei

Kopiere nun den Inhalt aus der docker-compose.yml.txt Datei in deine eben erstellte .yml datei und passe es entsprechend an.

Anschließend kann der Container ausgerollt werden.

```sh
docker-compose up -d
```

## Domain über Proxy Manager mit der IP Adresse verknüpfen

Als nächstes die Domain mit der IP-Adresse des Vaultwarden verknüpfen und die SSL verschlüselung aktivieren.
