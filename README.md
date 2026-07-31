# Zagiya — Découvrir Cursor en pratique

**Zagiya** est un dépôt de démonstration pour les débutants qui souhaitent comprendre la puissance de [Cursor](https://cursor.com) — un IDE (environnement de développement intégré) assisté par intelligence artificielle.

> Cursor n'est pas seulement un éditeur de code. C'est un environnement où vous pouvez, en langage naturel, créer des sites web, analyser des données, automatiser des tâches, gérer des fichiers — littéralement tout ce qu'on fait sur un ordinateur.

## Démarrage rapide

1. **Ouvrez ce dossier dans Cursor** : `Fichier → Ouvrir le dossier` → sélectionnez `Zagiya`
2. **Ouvrez le chat Agent** (panneau latéral ou `Ctrl+L`)
3. **Essayez l'une de ces commandes** :

| Commande à taper dans le chat | Ce qui se passe |
|-------------------------------|-----------------|
| « Affiche la landing page en local » | Lance un serveur web et ouvre la page |
| « Analyse les prospects CSV » | Lit et résume les données de vente |
| « Explique-moi la configuration Cursor de ce dépôt » | Tour guidé des rules, skills et agents |
| « Montre-moi comment configurer Cursor pour mon propre projet » | Guide pas à pas |

## Structure du dépôt

```
Zagiya/
├── README.md                 ← Vous êtes ici
├── AGENTS.md                 ← Instructions pour l'agent Cursor
├── .cursor/
│   ├── rules/                ← Règles persistantes (contexte auto)
│   ├── skills/               ← Compétences spécialisées
│   └── agents/               ← Sous-agents personnalisés
└── demo/
    ├── landing-page/         ← Partie 1 : page web
    └── data/                 ← Partie 2 : CSV de prospects
```

## Partie 1 — Afficher une page web en local

Le dossier `demo/landing-page/` contient une page d'accueil simple (HTML + CSS, sans framework).

**Manuellement :**
```bash
cd demo/landing-page
python -m http.server 8080
```
Puis ouvrez **http://localhost:8080** dans votre navigateur.

**Avec Cursor :** demandez simplement *« Lance la landing page »* — l'agent exécutera la commande pour vous.

## Partie 2 — Analyser une liste CSV

Le fichier `demo/data/prospects.csv` contient 20 prospects fictifs (nom, email, entreprise, secteur, statut, montant estimé).

**Avec Cursor :** demandez *« Analyse le fichier prospects.csv »* ou *« Quels prospects dois-je relancer ? »*

L'agent peut :
- Compter les prospects par statut
- Calculer la valeur totale du pipeline
- Identifier les secteurs les plus représentés
- Lister les contacts à relancer

## Configuration Cursor expliquée

### Règles (`.cursor/rules/`)

Des fichiers `.mdc` avec des instructions que l'agent reçoit **automatiquement** selon le contexte :

| Fichier | Rôle |
|---------|------|
| `demo-welcome.mdc` | Accueil et orientation (toujours actif) |
| `landing-page.mdc` | Conventions pour la page web |
| `csv-analysis.mdc` | Conventions pour l'analyse CSV |

### Skills (`.cursor/skills/`)

Des workflows spécialisés que l'agent charge quand c'est pertinent :

| Skill | Usage |
|-------|-------|
| `serve-landing-page` | Lancer le serveur local |
| `analyze-csv-prospects` | Analyser les listes de prospects |

### Agents (`.cursor/agents/`)

Des sous-agents avec des prompts dédiés. Exemple : `demo-guide` — formateur pour débutants.

### Cloud Agents

Les règles et skills versionnés dans `.cursor/` sont **automatiquement disponibles** quand vous utilisez un Cloud Agent sur ce dépôt. Clonez le repo, lancez un agent cloud — la configuration voyage avec le code.

## Configurer votre propre projet

Pour reproduire cette configuration sur un autre dépôt :

1. Créez `.cursor/rules/` et ajoutez un fichier `.mdc` avec `alwaysApply: true`
2. Créez `.cursor/skills/mon-skill/SKILL.md` pour vos workflows récurrents
3. Ajoutez un `AGENTS.md` à la racine pour les instructions globales
4. Versionnez tout dans Git — votre équipe en bénéficie aussi

Demandez à Cursor : *« Aide-moi à créer une règle pour mon projet »* — il utilisera les skills intégrés `create-rule` et `create-skill`.

## Licence

Démo libre d'utilisation pour la formation et la découverte de Cursor.
