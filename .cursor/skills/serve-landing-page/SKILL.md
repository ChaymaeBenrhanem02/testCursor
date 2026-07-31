---
name: serve-landing-page
description: Lance un serveur de développement local pour afficher la page d'accueil démo dans demo/landing-page/. Use when the user wants to preview, view, or serve the landing page locally, open localhost, or demonstrate a simple web page.
---

# Afficher la landing page en local

## Fichiers

- `demo/landing-page/index.html`
- `demo/landing-page/styles.css`

## Workflow

1. Vérifier que les fichiers existent
2. Lancer un serveur HTTP depuis `demo/landing-page/` :

```bash
# Bash / macOS / Linux
cd demo/landing-page && python -m http.server 8080

# PowerShell (Windows)
Set-Location demo/landing-page; python -m http.server 8080
```

3. Indiquer à l'utilisateur d'ouvrir **http://localhost:8080** dans son navigateur
4. Exécuter la commande vous-même (en arrière-plan si nécessaire)
5. Expliquer brièvement : un serveur local sert les fichiers HTML/CSS au navigateur — c'est ainsi que les développeurs testent des sites

## Alternative sans Python

```bash
npx --yes serve demo/landing-page -p 8080
```

## Dépannage

- Port 8080 occupé → essayer 3000 ou 5500
- Windows : `python` ou `py -m http.server 8080`
