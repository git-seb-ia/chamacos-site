# Journal de développement — Mise en place Git & automatisations CHAMACOS

## Objectif

l’objectif était de transformer le projet site statique CHAMACOS en véritable projet portfolio documenté et versionné via GitHub.

Le but est de montrer :

- architecture réelle
- automatisation n8n
- intégration IA
- gestion de contenu dynamique
- workflows Telegram
- déploiement VPS
- environnement Docker local

---

# Création du repository GitHub

Création du repository :

```text
chamacos-site
```

Connexion du VPS au repository distant via SSH.

---

# Mise en place environnement Docker local

Création environnement local CHAMACOS :

- Docker Compose
- Nginx
- PHP-FPM

Architecture :

```text
Navigateur
    ↓
Nginx container
    ↓
PHP-FPM container
```

---

## Problème PHP détecté

Les fichiers `.php` étaient téléchargés au lieu d’être exécutés.

Cause :

```text
Nginx seul sans PHP-FPM
```

---

## Correction

Ajout d’un service PHP-FPM dans :

```text
docker-compose.yml
```

Création configuration :

```text
nginx/default.conf
```

avec :

```nginx
location ~ \.php$
```

Configuration FastCGI vers :

```text
php:9000
```

Résultat :

- exécution PHP fonctionnelle
- environnement local opérationnel

---

# Automatisations Telegram

## Galerie principale

Workflow :

```text
Telegram Bot
    ↓
n8n Trigger
    ↓
Upload VPS
    ↓
gallery.json
```

---

## Galerie concerts

Création :

- nouveau bot Telegram
- nouveau credential n8n
- nouveau workflow

---

## Problème détecté

Le trigger Telegram ne recevait aucun événement.

Diagnostic :

```text
/webhook-test/ bloqué par Nginx
```

---

## Correction Nginx

Ajout du bloc :

```nginx
location /webhook-test/
```

Les webhooks Telegram de test sont désormais accessibles publiquement.

Résultat :

- plusieurs workflows Telegram actifs simultanément
- galerie principale opérationnelle
- galerie concerts opérationnelle

---

# Formulaire de contact automatisé

Création d’un formulaire contact connecté directement à n8n via webhook.

Architecture :

```text
Frontend contact form
    ↓
Webhook n8n
    ↓
Validation anti-spam
    ↓
Telegram notification
    ↓
Email notification
```

---

## Sécurité formulaire

Ajout :

- validation email
- validation téléphone
- anti injection HTML/JS
- honeypot anti-spam

---

# Technologies utilisées

## Frontend

- HTML5
- CSS3
- JavaScript Vanilla

## Backend / automation

- n8n
- Webhooks
- Telegram Bot API
- SMTP Gmail

## Infrastructure

- Ubuntu VPS
- Docker
- Docker Compose
- Nginx
- HTTPS / Certbot
- SSH

## Versioning

- Git
- GitHub

---

# Résultat actuel

Le projet CHAMACOS est maintenant :

- versionné sur GitHub
- documenté
- automatisé
- déployé sur VPS
- reproductible en local
- piloté par workflows n8n

Le projet démontre désormais :

- automatisation de contenu
- orchestration workflows
- intégration IA
- webhooks
- gestion JSON
- Docker
- reverse proxy
- architecture légère moderne


