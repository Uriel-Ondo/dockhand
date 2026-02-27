
# Dockhand ⚓️

[![GitHub release](https://img.shields.io/github/v/release/fnsys/dockhand?style=flat-square)](https://github.com/fnsys/dockhand/releases)
[![Docker pulls](https://img.shields.io/docker/pulls/fnsys/dockhand?style=flat-square)](https://hub.docker.com/r/fnsys/dockhand)
[![License](https://img.shields.io/badge/license-BSL%201.1%20→%20Apache%202.0%20(2029)-blue?style=flat-square)](https://github.com/fnsys/dockhand/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/fnsys/dockhand?style=flat-square)](https://github.com/fnsys/dockhand/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/fnsys/dockhand?style=flat-square)](https://github.com/fnsys/dockhand/issues)

Dockhand est une solution moderne et intuitive pour l’administration des environnements Docker.  
Alternative à Portainer, elle offre une interface claire, des fonctionnalités avancées et une installation simplifiée.  
Gratuite pour les particuliers (Homelab), une version professionnelle est disponible pour les entreprises.

👉 [Projet GitHub - Dockhand](https://github.com/fnsys/dockhand)  
👉 [Site officiel - Dockhand](https://dockhand.io)

---

## ✨ Fonctionnalités principales

### 🐳 Gestion des conteneurs
- Démarrer, arrêter, redémarrer, supprimer des conteneurs
- Créer des conteneurs via Docker ou Docker Compose
- Supervision détaillée (processus, stockage, variables, logs, ressources…)
- Terminal intégré (sans SSH)
- Parcourir les données stockées dans les conteneurs
- Gestion des réseaux, registres et volumes

### ⚙️ Déploiement & GitOps
- Éditeur visuel pour stacks Docker Compose (YAML)
- Intégration Git native (déploiement depuis repo, auto-deploy via Webhooks)
- Mises à jour planifiées et synchronisations automatiques

### 📊 Observabilité
- Métriques live (CPU, RAM par conteneur)
- Logs en temps réel
- Suivi du disque et nettoyage des images orphelines
- Historique complet de l’activité des conteneurs

### 🔒 Sécurité
- Authentification SSO (OIDC, LDAP/AD en version pro)
- RBAC (gestion des droits utilisateurs – version entreprise)
- Scan de vulnérabilités (Grype, Trivy) intégré dans la version gratuite

### 🌐 Multi-hôtes & Réseau
- Gestion de plusieurs hôtes Docker
- Agent **Hawser** pour connecter des environnements distants
- Connexions TLS sécurisées
- Compatibilité totale avec vos fichiers `docker-compose.yml`

---

## 📜 Licence

Dockhand utilise actuellement la **Business Source License (BSL 1.1)**.  
- Gratuit pour un usage personnel (Homelab)  
- Licence payante pour usage en entreprise  
- Conversion automatique prévue en **Apache 2.0 en 2029**  

---

## ⚙️ Installation avec Docker Compose

### Prérequis
- Docker installé (Debian, Linux, ou Docker Desktop)
- Docker Compose

### Étapes
```bash
# Créer le répertoire
sudo mkdir -p /opt/docker-compose/dockhand/data
cd /opt/docker-compose/dockhand
nano docker-compose.yml
```

### Exemple de `docker-compose.yml`
```yaml
services:
  dockhand:
    image: fnsys/dockhand:latest
    container_name: dockhand
    restart: unless-stopped
    ports:
      - "3000:3000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - ./data:/app/data
```

### Lancer le conteneur
```bash
docker compose up -d
```

Accéder à l’interface :  
- Local : `http://localhost:3000`  
- Distant : `http://<IP_ou_hostname>:3000`

---

## 🖥️ Prise en main

- **Ajout d’un serveur Docker** : via `Settings > Environments` (socket Unix `/var/run/docker.sock`)  
- **Création d’un compte utilisateur** : gestion des comptes, SSO/OIDC, MFA (TOTP)  
- **Gestion des conteneurs** : vue détaillée (image, uptime, ressources, ports, stack associée)  
- **Stacks Docker Compose** : adoption des projets existants, édition graphique, gestion des variables `.env`  
- **Images Docker** : visualisation, suppression des images inutilisées, scan de vulnérabilités  
- **Notifications** : intégration SMTP & Apprise (Discord, Slack, Telegram, Gotify, Ntfy…)

---

## 📌 Conclusion

Dockhand est un outil puissant et moderne pour administrer vos environnements Docker.  
Il combine simplicité d’installation, observabilité en temps réel, sécurité renforcée et gestion multi-hôtes.  
Un allié idéal pour votre Homelab ou vos projets professionnels.
