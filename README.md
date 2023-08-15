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
 
---

