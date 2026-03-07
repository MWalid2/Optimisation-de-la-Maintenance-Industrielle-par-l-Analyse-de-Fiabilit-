# Projet Statistiques — Fiabilité & Maintenance

Analyse statistique de la fiabilité de systèmes à partir de simulations Monte Carlo, avec estimation des paramètres et optimisation de la politique de maintenance.

## Contenu

| Partie | Description |
|--------|-------------|
| **1. Visualisation** | Génération d'un échantillon Weibull (β=2, η=3), histogramme, courbe de fiabilité R(t) et taux de défaillance λ(t) |
| **2. Estimation** | Estimation de β et η par régression linéaire sur papier de Weibull |
| **3. Architecture** | Comparaison série vs parallèle sur composants exponentiels |
| **4. Maintenance** | Survie conditionnelle, espérance de vie résiduelle, politique de remplacement préventif optimal |

## Stack

- Python 3.13
- `numpy`, `scipy`, `matplotlib`, `seaborn`, `pandas`
- Environnement géré avec [uv](https://docs.astral.sh/uv/)

## Lancer le projet

```bash
uv sync
jupyter notebook partie_3.ipynb
```
