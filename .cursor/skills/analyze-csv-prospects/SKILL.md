---
name: analyze-csv-prospects
description: Analyse des fichiers CSV de prospects commerciaux (statuts, secteurs, pipeline, relances). Use when the user wants to analyze CSV data, prospect lists, leads, sales pipeline, or demo/data/prospects.csv.
---

# Analyser une liste de prospects CSV

## Fichier exemple

`demo/data/prospects.csv` — 20 prospects fictifs avec colonnes :
nom, email, entreprise, secteur, statut, date_contact, montant_estime

## Workflow

1. Lire le CSV et afficher un aperçu (5 premières lignes)
2. Produire un **résumé exécutif** :
   - Total prospects
   - Répartition par statut
   - Top 3 secteurs
   - Valeur totale du pipeline (montant_estime)
   - Prospects à relancer (statut = contacté)
3. Présenter les résultats en **tableau markdown** ou canvas si les données sont riches
4. Proposer des analyses supplémentaires selon la demande

## Script rapide (Python)

```python
import csv
from collections import Counter
from pathlib import Path

path = Path("demo/data/prospects.csv")
rows = list(csv.DictReader(path.open(encoding="utf-8")))

statuts = Counter(r["statut"] for r in rows)
secteurs = Counter(r["secteur"] for r in rows)
pipeline = sum(int(r["montant_estime"]) for r in rows)
a_relancer = [r for r in rows if r["statut"] == "contacté"]

print(f"Total: {len(rows)} prospects")
print(f"Pipeline: {pipeline:,} €")
print("Par statut:", dict(statuts))
print("Top secteurs:", secteurs.most_common(3))
print(f"À relancer: {len(a_relancer)}")
```

Exécuter le script plutôt que de seulement le montrer.

## Statuts possibles

`nouveau` | `contacté` | `qualifié` | `gagné` | `perdu`
