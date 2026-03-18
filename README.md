# PricePred - Estimation de Prix d'Objets d'Occasion (FR/AR)

![Badge PricePred](https://img.shields.io/badge/Statut-Déploiement_Immédiat-brightgreen?style=for-the-badge)

## Résumé

PricePred est une application web d’estimation de prix de revente d’objets d’occasion (voitures, téléphones, ordinateurs, montres, caméras, autres). L’application fonctionne en Français et en Arabe, et fournit :

- estimation heuristique locale basée sur âge/état/catégorie
- option IA via Hugging Face `HF_API_KEY` (modèle Qwen)
- interface légère Flask + HTML/CSS
- thèmes clair/sombre

## Objectif

Permettre aux acheteurs/vendeurs de vérifier rapidement un prix estimé pour un objet d’occasion en dirhams marocains (MAD), avec une estimation cohérente et un retour clair sur l’état de l’objet.

## Fonctionnalités

- Formulaire de saisie : catégorie, marque, modèle, année, état
- Bilingue FR/AR
- Estimation IA + fallback heuristique
- Routes de déploiement Vercel configurées
- Assets inclus dans déploiement (`templates/`, `static/`)

## Déploiement local

1. Cloner le repo :

```bash
git clone https://github.com/Aya-dev-creator/NPricePred.git
cd NPricePred
```

2. Créer un environnement virtuel :

```bash
python -m venv .venv
.venv\Scripts\activate   # Windows
# source .venv/bin/activate  # macOS/Linux
pip install -r requirements.txt
```

3. Optionnel : définir `HF_API_KEY` :

```bash
set HF_API_KEY=your_token  # Windows
# ou export HF_API_KEY=your_token  # macOS/Linux
```

4. Lancer le serveur :

```bash
python api/index.py
```

Visiter `http://127.0.0.1:5000`.

## Déploiement Vercel

`vercel.json` :

```json
{
  "version": 2,
  "builds": [
    {
      "src": "api/index.py",
      "use": "@vercel/python",
      "config": {"includeFiles": ["templates/**", "static/**"]}
    }
  ],
  "routes": [{"src": "/(.*)", "dest": "/api/index.py"}]
}
```

## Structure du projet

```
NPricePred/
├── api/index.py
├── templates/index.html
├── static/styles.css
├── requirements.txt
├── vercel.json
└── README.md
```

## Remarques

- Ne pas versionner `HF_API_KEY` dans le dépôt.
- L’approche heuristique fonctionne sans API externe.
## 🎯 Objectif du Projet

Fournir une interface simple, bilingue (français/arabe) et réactive pour évaluer rapidement le prix de revente d’un objet sur la base de caractéristiques utilisateur : catégorie, marque, modèle, année, état.

### ✅ Cas d’usage

- Vendeur qui souhaite fixer un tarif de vente juste.
- Acheteur qui veut vérifier la raisonabilité d’une annonce.
- Estimation rapide lors de transactions entre particuliers.

---

## ✨ Fonctionnalités Clés

- Bilingue : Français et arabe.
- Thèmes clair/sombre.
- Estimation IA via Hugging Face (optionnelle) avec clé `HF_API_KEY`.
- Mode heuristique local de secours (calcul basé sur âge, condition, catégorie).
- Front web en Flask avec modèles HTML/CSS.
- Inclut templates statiques dans le déploiement Vercel.

---

## 🚀 Démo en local

1. Cloner le repo :

```bash
git clone https://github.com/Aya-dev-creator/NPricePred.git
cd NPricePred
```

2. Installer l’environnement :

```bash
python -m venv .venv
.venv\Scripts\activate      # Windows
# ou source .venv/bin/activate  # macOS/Linux
pip install -r requirements.txt
```

3. Définir la clé API (optionnel) :

```bash
set HF_API_KEY=your_token
# ou PowerShell : $env:HF_API_KEY='your_token'
```

4. Lancer l’application :

```bash
python api/index.py
```

5. Ouvrir : `http://127.0.0.1:5000`

---

## ⚙️ Déploiement Vercel

Fichier de config `vercel.json` :

```json
{
  "version": 2,
  "builds": [
    {
      "src": "api/index.py",
      "use": "@vercel/python",
      "config": {
        "includeFiles": ["templates/**", "static/**"]
      }
    }
  ],
  "routes": [{ "src": "/(.*)", "dest": "/api/index.py" }]
}
```

- Repo : `Aya-dev-creator/NPricePred`
- Optionnel : command `pip install -r requirements.txt`

---

## 📂 Structure du projet

```text
NPricePred/
├── api/index.py         # Backend Flask + logique prix
├── templates/index.html # Interface HTML FR/AR
├── static/styles.css    # CSS Thèmes clair / sombre
├── requirements.txt
├── vercel.json
├── README.md
└── ...
```

---

## 🔐 Environnement et sécurité

- `HF_API_KEY` (Hugging Face) pour la partie IA.
- Ne mettez aucune clé en clair dans le dépôt.

---

</div>


