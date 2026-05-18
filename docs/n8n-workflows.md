# n8n Workflows

## Présentation

Le projet CHAMACOS repose sur plusieurs workflows n8n permettant de piloter automatiquement le contenu du site.

---

# Workflow : génération automatique de contenu IA

## Fonctionnement

```text
Cron Trigger
    ↓
Lecture main-text.json
    ↓
Extraction ancien contenu
    ↓
Construction prompt IA
    ↓
HTTP Request API IA
    ↓
Validation réponse HTML
    ↓
Nettoyage contenu
    ↓
Écriture main-text.json
```

---

## Objectif

Mettre à jour automatiquement le contenu éditorial du site avec un texte généré par IA.

---

## Fonctionnalités

- lecture du contenu actuel
- génération d'un texte différent
- contrôle HTML strict
- stockage JSON
- contenu dynamique côté frontend

---

# Workflow : upload Telegram → galerie

## Fonctionnement

```text
Telegram Trigger
    ↓
Réception image
    ↓
Traitement binaire
    ↓
Upload serveur VPS
    ↓
Mise à jour gallery.json
```

---

## Objectif

Permettre l'ajout d'images dans la galerie du site directement depuis un smartphone.

---

## Fonctionnalités

- réception automatique des photos
- upload serveur distant via SSH
- gestion JSON dynamique
- galerie temps réel

---

# Workflow : notifications système

## Fonctionnement

```text
Déclencheur
    ↓
Analyse état workflow
    ↓
Notification
```

---

# Utilisation de n8n

## Mode de déploiement

- n8n self-hosted
- Docker
- reverse proxy Nginx

---

# Compétences démontrées

- orchestration
- API
- gestion JSON
- automatisation
- traitement binaire
- gestion fichiers serveur
- logique conditionnelle
- workflows temps réel
