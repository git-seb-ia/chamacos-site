# Telegram Upload Flow

## Objectif

Permettre l'ajout automatique de photos dans la galerie CHAMACOS depuis Telegram.

---

# Workflow global

```text
Utilisateur Telegram
        ↓
Bot Telegram
        ↓
Telegram Trigger n8n
        ↓
Récupération fichier binaire
        ↓
Traitement image
        ↓
Upload SSH vers VPS
        ↓
Mise à jour gallery.json
        ↓
Affichage automatique sur le site
```

---

# Détails techniques

## Réception image

Le workflow utilise un `Telegram Trigger`.

Les images sont reçues sous forme binaire dans :

```text
binary.data
```

---

## Upload serveur

Les images sont transférées automatiquement sur le VPS via :

- SSH
- SCP
- commandes Linux

---

# Avantages

- publication ultra rapide
- aucun back-office nécessaire
- fonctionnement mobile-first
- automatisation complète

---

# Technologies

- Telegram Bot API
- n8n
- SSH
- JSON
- VPS Linux


- Ajout d'un second bot pour alimenter page concerts
Chamacos Gallery Bot
Chamacos Concerts Bot

- Telegram Bot2 API
- n8n
- SSH
- JSON
- VPS Linux


