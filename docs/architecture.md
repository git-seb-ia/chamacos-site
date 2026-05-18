# CHAMACOS - Architecture Technique

## Présentation

CHAMACOS est un site statique enrichi par plusieurs automatisations pilotées par n8n.

Le projet combine :

- site statique HTML/CSS/JavaScript
- contenu dynamique via fichiers JSON
- génération de texte par IA
- automatisation de publication
- upload d'images via Telegram
- déploiement VPS Linux

---

# Architecture globale

```text
                    ┌──────────────────┐
                    │   API IA / LLM   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │       n8n        │
                    │  self-hosted     │
                    └───────┬──────────┘
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
        ▼                   ▼                   ▼

 Lecture JSON      Génération contenu     Telegram Trigger
 contenu actuel          IA                Upload images

        │                   │                   │
        ▼                   ▼                   ▼

   Validation         Nettoyage HTML      Upload VPS SSH

        │                   │                   │
        └──────────────┬────┴───────────────────┘
                       ▼

             Mise à jour fichiers JSON

                       ▼

                Site statique CHAMACOS
```

---

# Technologies utilisées

## Frontend

- HTML5
- CSS3
- JavaScript Vanilla

## Backend / Automatisation

- n8n self-hosted
- Node-based workflows
- Webhooks
- Cron jobs

## Infrastructure

- VPS Linux Ubuntu
- Docker
- Docker Compose
- Nginx
- HTTPS / Certbot
- SSH

## IA

- API LLM externe
- génération HTML dynamique
- contrôle de cohérence
- validation de structure HTML

---

# Stockage des données

Le site utilise des fichiers JSON comme mini-CMS :

- `main-text.json`
- `gallery.json`

Cela permet :

- simplicité
- rapidité
- absence de base SQL
- compatibilité parfaite avec un site statique

---

# Sécurité

- accès n8n protégé via Nginx
- restriction IP sur l'interface
- webhooks publics séparés
- authentification SSH par clés

---

# Objectifs du projet

Ce projet démontre :

- automatisation de contenu
- orchestration de workflows
- intégration IA
- architecture légère mais réelle
- déploiement autonome
- gestion d'API
- intégration Telegram
