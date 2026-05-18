# AI Content Generation

## Objectif

Automatiser la génération du contenu éditorial du site CHAMACOS via une API IA.

---

# Fonctionnement général

```text
Lecture contenu actuel
        ↓
Construction prompt
        ↓
Envoi API IA
        ↓
Réception HTML
        ↓
Validation
        ↓
Nettoyage
        ↓
Écriture JSON
```

---

# Contraintes imposées au modèle IA

Le workflow impose :

- HTML strict
- aucune sortie Markdown
- structure fixe
- contenu différent du précédent

---

# Exemple de structure demandée

```html
<h4>Titre</h4>
<div class="line-dec"></div>
<p>Contenu</p>
```

---

# Validation du contenu

Le workflow vérifie :

- cohérence HTML
- présence des balises attendues
- absence de texte parasite
- nettoyage espaces et caractères invalides

---

# Objectifs techniques

Ce workflow démontre :

- intégration API IA
- prompt engineering
- validation automatique
- génération dynamique de contenu
- automatisation éditoriale

---

# Stack technique

- n8n
- HTTP Request
- JSON
- JavaScript
- API IA externe
