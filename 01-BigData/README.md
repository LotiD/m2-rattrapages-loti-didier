# Analyse des radars fixes en France

## Description

Ce projet explore et nettoie le jeu de données open data recensant les radars fixes en France (numéro, type, date de mise en service, vitesse maximale autorisée, coordonnées GPS). Le notebook Jupyter couvre :

- Le chargement et le nettoyage des données (encodage, séparateur, types, valeurs manquantes, doublons, coordonnées aberrantes)
- L'analyse par type de radar (ETD, ETF, ETT, ETU, ETVM, ETFR, ETPN) et l'identification des cas où la VMA (Vitesse Maximale Autorisée) est structurellement absente
- Des visualisations : répartition des radars par VMA, évolution du nombre d'installations par année, cartographie des radars

## Source des données

Jeu de données : *Liste des radars fixes en France* (https://www.data.gouv.fr/datasets/liste-des-radars-fixes-en-france), format CSV, séparateur `;`, encodage Latin-1.

## Prérequis

- Python 3.9+
- Jupyter Notebook (ou JupyterLab)

## Installation

1. Cloner ou télécharger ce projet, et placer le fichier CSV dans le même dossier que le notebook.

2. Installer les dépendances :

```bash
pip install pandas matplotlib folium
```

Ou, si vous utilisez Anaconda :

```bash
conda install pandas matplotlib
conda install -c conda-forge folium
```

3. Lancer Jupyter Notebook :

```bash
jupyter notebook
```

4. Ouvrir le notebook et exécuter les cellules dans l'ordre (Kernel → Restart Kernel and Run All recommandé après toute modification en amont, pour éviter les états incohérents entre cellules).

## Dépendances principales

| Librairie | Usage |
|---|---|
| `pandas` | Chargement, nettoyage et manipulation des données tabulaires |
| `matplotlib` | Graphiques (bar chart, camembert, courbes) |
| `folium` | Cartes interactives des radars |

## Structure des données

| Colonne | Description |
|---|---|
| Numéro de radar | Identifiant unique du radar |
| Type de radar | ETD, ETF, ETT, ETU, ETVM, ETFR, ETPN |
| Date de mise en service | Date d'installation du radar |
| VMA | Vitesse Maximale Autorisée (km/h) — absente pour les radars ETFR (feu rouge) et ETPN (passage à niveau) |
| Latitude / Longitude | Coordonnées GPS du radar |