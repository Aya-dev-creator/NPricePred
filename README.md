# 🏷️ Prédicteur de Prix d'Objets d'Occasion (FR/AR)

Une application web intelligente et bilingue qui aide les utilisateurs à estimer rapidement le prix de revente de divers objets d'occasion — tels que des voitures, des téléphones, des ordinateurs, des montres et des caméras — en **Dirhams Marocains (MAD)**.

---

## 🎯 Objectif

L'objectif principal de ce projet est de fournir un outil rapide, accessible et convivial pour estimer la valeur marchande d'occasion des objets du quotidien. Que vous soyez acheteur ou vendeur, cette application vous donne une estimation pédagogique basée sur l'âge, l'état, la marque et la catégorie de l'objet.

## ✨ Ce qui la rend spéciale

- **🧠 Estimations Propulsées par l'IA :** S'intègre à l'API de Hugging Face (utilisant le modèle `Qwen2.5-72B-Instruct`) pour agir comme un expert du marché marocain et fournir des prix réalistes basés sur les spécificités de l'objet.
- **📉 Système de Secours Intelligent :** Si l'IA est indisponible, l'application bascule en douceur vers un modèle d'amortissement heuristique personnalisé, adapté à chaque catégorie d'objet.
- **🌍 Interface Bilingue :** L'application prend en charge nativement le **Français** et l'**Arabe**, ce qui la rend largement accessible aux utilisateurs au Maroc et ailleurs.
- **🌗 Thèmes UI Personnalisés :** Propose des modes **Clair et Sombre** basés sur CSS que les utilisateurs peuvent basculer facilement.
- **⚡ Légère :** Construite purement en Python (Flask) et HTML/CSS. Aucune dépendance JavaScript complexe n'est requise pour l'expérience de base.

---

## 🚀 Comment utiliser l'application

1. **Accéder à l'application** : Ouvrez votre navigateur web et allez à l'URL locale (généralement `http://127.0.0.1:5000`).
2. **Définir les préférences** : En haut de la page, choisissez votre langue préférée (Français / العربية) et votre thème (Sombre / Clair), puis cliquez sur "Appliquer".
3. **Choisir une catégorie** : Sélectionnez le type d'objet que vous souhaitez évaluer (ex: Voiture, Téléphone, Ordinateur, Montre, Caméra ou Autre).
4. **Saisir les détails** : Remplissez le formulaire avec les détails de l'objet :
   - **Marque** & **Modèle**
   - **Année** d'achat/fabrication
   - **État** (ex: "Comme neuf", "Bon état", "Abîmé")
5. **Obtenir l'estimation** : Soumettez le formulaire. L'application calculera et affichera le prix estimé en **MAD**, accompagné d'un résumé détaillé.

> ⚠️ **Avertissement :** Cet outil fournit une estimation approximative et pédagogique. Ce n'est pas une expertise professionnelle.

---

## 🛠️ Comment l'installer (Configuration)

### Prérequis

- **Python 3.10+** installé sur votre système.
- **Git** (optionnel, pour cloner le dépôt).
- Une **Clé API Hugging Face** (pour la fonctionnalité d'estimation par IA).

### 1. Cloner ou Télécharger le Projet

Accédez au dossier de votre choix et clonez le dépôt :

```bash
git clone <url_du_depot>
cd app
```

*(Si vous n'utilisez pas Git, téléchargez simplement les fichiers du projet dans un dossier nommé `app`.)*

### 2. Créer un Environnement Virtuel (Recommandé)

**Windows :**
```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux / macOS :**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Installer les Dépendances

Installez les packages Python requis (Flask, huggingface_hub, etc.) :

```bash
pip install -r requirements.txt
```

### 4. Configurer les Variables d'Environnement

Pour activer les prédictions par IA, définissez votre clé API Hugging Face comme variable d'environnement dans votre terminal :

**Windows (Invite de commande) :**
```cmd
set HF_API_KEY=votre_token_huggingface_ici
```

**Windows (PowerShell) :**
```powershell
$env:HF_API_KEY="votre_token_huggingface_ici"
```

**Linux / macOS :**
```bash
export HF_API_KEY="votre_token_huggingface_ici"
```

### 5. Lancer l'Application

Démarrez le serveur de développement Flask :

```bash
python api/index.py
```

L'application sera alors accessible sur `http://127.0.0.1:5000`.
Pour arrêter le serveur, appuyez sur `Ctrl + C` dans votre terminal.

---

## 📂 Structure du Projet

```text
app/
├── api/
│   └── index.py        # Serveur Backend Flask (Point d'entrée Vercel)
├── vercel.json         # Configuration de déploiement Vercel
├── requirements.txt    # Dépendances Python
├── templates/
│   └── index.html      # Template HTML principal (UI FR/AR)
└── static/
    └── styles.css      # Styles CSS (Mise en page, modes Sombre/Clair)
```

## 🔧 Améliorations Futures

- Remplacer totalement les heuristiques par des modèles de ML entraînés sur de vraies annonces marocaines.
- Ajouter des cookies/stockage local pour mémoriser la langue et le thème préférés.
- Se connecter à des APIs d'e-commerce en direct pour récupérer les prix moyens du marché en temps réel.
