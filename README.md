# 🚀 IIoT Industrial HVAC Supervision & Control System

> Un projet complet d'automatisation et de supervision industrielle combinant la robustesse d'un automatisme Siemens (TIA Portal / S7-1200) avec la flexibilité des technologies IIoT modernes (Node-RED, Telegram Bot, WinCC).

---

## 📌 Architecture du Système

Le système repose sur une architecture industrielle multi-niveaux :
* **Niveau Automatisme (PLC) :** Siemens S7-1200 sous TIA Portal pour la logique séquentielle, la régulation thermique et les sécurités logiques (`Interlock`).
* **Passerelle de Communication :** Mapping du port S7 via **NetToPLCSIM** pour établir la liaison ISO-on-TCP avec Node-RED.
* **Supervision & IHM :** Siemens WinCC pour la supervision SCADA locale, Node-RED Dashboard pour la supervision Web et Telegram Bot API pour la télégestion à distance.

---

## ⚙️ Fonctionnalités Techniques

### 1. Cœur Automatisme (Siemens TIA Portal)
* **Traitement Analogique :** Conversion en temps réel de la température via variable interne *(prêt pour raccordement direct à un capteur réel)*.
* **Régulation Thermique Intelligente :**
  - **T < 18°C :** Activation du chauffage (aérothermes) + 1 groupe (3 ventilateurs) avec roulement *(extinction automatique du chauffage dès 22°C)*.
  - **18°C < T < 25°C :** Activation de 2 groupes (6 ventilateurs) avec roulement.
  - **T > 30°C :** Activation maximale des 9 ventilateurs à 100 %.
* **Roulement & Horodatage :** Équilibrage automatique des heures de fonctionnement des moteurs basé sur l'heure de démarrage du mode `AUTO` *(7 jours en réel / 1 min en démo)*.
* **Sécurité Interlock :** Verrouillage logique anti-conflit entre les modes `AUTO` et `MANU`.

### 2. Interface IIoT & Telegram Bot (Node-RED Middleware)
* **Passerelle Réseau :** Connexion directe ISO-on-TCP entre PLCSIM et Node-RED via **NetToPLCSIM**.
* **Sécurité & Session :** Authentification par mot de passe (`login`/`logout`) et maintien de session (`global.set`).
* **Notifications Push Événementielles :** Envoi automatique d'une notification d'alarme unique dès l'apparition d'un défaut *(système anti-spam)*.
* **Commandes & Planification :** Extraction et injection (`insert`) de 5 paramètres temporels (`auto JJ/MM HH:MM`) directement dans l'automate.

### 3. Supervision Multi-Interface
* **Siemens WinCC :** Interface SCADA locale synchronisée en temps réel.
* **Node-RED Dashboard :** Interface Web pour le contrôle manuel direct et le suivi visuel des états.

---

## 🎥 Démo Vidéo du Projet

Voici un aperçu du système en fonctionnement (simulation PLC, supervision et contrôle à distance) :

*(Glissez-déposez votre fichier vidéo `.mp4` ici dans l'éditeur GitHub)*

---

## 🛠️ Stack Technique
`Siemens TIA Portal (S7-1200)` | `NetToPLCSIM` | `Siemens WinCC` | `Node-RED Dashboard` | `Telegram Bot API` | `Industrial IoT`

---
programmation. Les fichiers sources du projet (fichiers TIA Portal et flux Node-RED) sont maintenus confidentiels et restent disponibles sur demande.*
