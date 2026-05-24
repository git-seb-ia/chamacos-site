
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
