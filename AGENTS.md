# Zagiya — Guide pour l'agent Cursor

Ce dépôt est une **démo pédagogique** pour les débutants qui découvrent Cursor. L'objectif est de montrer comment un IDE assisté par IA peut accélérer des tâches concrètes sur ordinateur.

## Contexte du projet

- **Public** : débutants, curieux, formateurs
- **Langue** : répondre en **français** sauf demande contraire
- **Ton** : pédagogique, encourageant, concret — montrer *comment faire*, pas seulement expliquer

## Structure du dépôt

```
Zagiya/
├── demo/
│   ├── landing-page/    # Partie 1 — Afficher une page web en local
│   └── data/            # Partie 2 — Analyser des listes CSV
├── .cursor/
│   ├── rules/           # Règles persistantes (contexte automatique)
│   ├── skills/          # Compétences spécialisées (workflows guidés)
│   └── agents/          # Sous-agents personnalisés
└── README.md            # Point d'entrée pour les humains
```

## Comportement attendu de l'agent

Quand quelqu'un ouvre ce dépôt pour la première fois :

1. **Accueillir** brièvement et orienter vers le `README.md`
2. **Proposer deux démos** :
   - Partie 1 : lancer la page d'accueil en serveur local (`demo/landing-page/`)
   - Partie 2 : analyser le fichier `demo/data/prospects.csv`
3. **Exécuter** les commandes vous-même (ne pas se contenter de les lister)
4. **Expliquer** chaque étape en langage simple (IDE, terminal, agent, règles, skills)

## Conventions

- Modifications minimales et ciblées
- Pas de sur-ingénierie — c'est une démo, pas un produit
- HTML/CSS vanilla pour la landing page (aucun build requis)
- CSV UTF-8 avec en-têtes en français
- Ne pas committer de secrets (`.env`, clés API)

## Skills du projet

| Skill | Quand l'utiliser |
|-------|------------------|
| `serve-landing-page` | Afficher la page web en local |
| `analyze-csv-prospects` | Analyser des prospects / listes CSV |

## Cloud Agents

Ce dépôt est compatible avec les **Cloud Agents** de Cursor : les règles (`.cursor/rules/`) et skills (`.cursor/skills/`) sont versionnés et disponibles dans l'environnement cloud lorsque le dépôt est cloné.
