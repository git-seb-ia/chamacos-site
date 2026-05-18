# Chamacos Website Automation
[link]chamacos.fr

Site statique du projet musical CHAMACOS, enrichi par des automatisations n8n et des contenus générés via API IA.

## Objectif

Ce projet montre comment un site statique peut être piloté par des workflows automatisés :

- mise à jour de texte via API IA
- stockage du contenu dans des fichiers JSON
- upload d’images via Telegram
- publication automatique vers le site
- orchestration avec n8n
- déploiement sur serveur VPS

## Stack

- HTML / CSS / JavaScript
- JSON comme mini-CMS
- n8n self-hosted
- Telegram Bot API
- API IA externe
- VPS Linux
- SSH
- Git / GitHub

## Fonctionnement général

1. n8n déclenche un workflow planifié ou manuel
2. le workflow lit le contenu actuel
3. une API IA génère une nouvelle version
4. le résultat est nettoyé et validé
5. le fichier JSON du site est mis à jour
6. le site recharge dynamiquement le contenu

## Automatisation images

Les images envoyées via Telegram sont récupérées par n8n, transférées vers le serveur, puis ajoutées à la galerie du site.

## Ce que ce projet démontre

- intégration API
- automatisation de contenu
- architecture simple mais réelle
- gestion de fichiers côté serveur
- workflow n8n documenté
- logique CMS sans base de données
