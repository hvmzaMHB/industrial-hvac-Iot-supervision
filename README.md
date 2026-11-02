# 🚀 IIoT Industrial HVAC Supervision & Control System

> **Système intelligent de régulation thermique et de supervision pour centrale HVAC industrielle**, combinant un automate Siemens S7-1200 (TIA Portal), une passerelle IIoT (NetToPLCSIM + Node-RED), un bot Telegram sécurisé et un SCADA WinCC.

---

## 📌 Architecture du Système
* **Niveau Automatisme (PLC) :** Siemens S7-1200 (TIA Portal) pour la logique séquentielle, les seuils thermiques et les sécurités `Interlock`.
* **Passerelle IIoT :** Connexion ISO-on-TCP via **NetToPLCSIM** pour lier le PLC à **Node-RED**.
* **Supervision & IHM :** Siemens WinCC (SCADA local), Node-RED Dashboard (Web) et Telegram Bot API (télégestion à distance).

---

## ⚙️ Fonctionnalités Clés
* **Régulation Thermique Intelligente :** Gestion automatique des aérothermes et des ventilateurs en fonction de paliers de température ($< 18^\circ\text{C}$, $18-25^\circ\text{C}$, $> 30^\circ\text{C}$).
* **Roulement & Horodatage :** Équilibrage automatique de l'usure des moteurs basé sur le temps de fonctionnement en mode `AUTO`.
* **Bot Telegram Sécurisé :** Authentification par mot de passe, notifications push d'alarmes anti-spam et injection de paramètres temporels (`auto JJ/MM HH:MM`) dans l'automate.
* **Sécurité Interlock :** Isolation stricte entre les modes `AUTO` et `MANU`.

---

## 🎥 Démo Vidéo du Projet

👉 **[Cliquez ici pour visionner la démonstration vidéo complète du système en action (Google Drive)]
((https://drive.google.com/file/d/1gjcQezAZSlfVJrsci0NO1CoV_KhyTbQG/view?usp=sharing))**

---

## 🛠️ Stack Technique
`Siemens TIA Portal (S7-1200)` | `NetToPLCSIM` | `Siemens WinCC` | `Node-RED Dashboard` | `Telegram Bot API` | `Industrial IoT`

---
