# Projet Statistiques — Fiabilité & Maintenance

Analyse statistique de la fiabilité de systèmes, avec estimation des paramètres, tests d'adéquation et analyse de sensibilité.

## Contenu

| Partie | Description |
|--------|-------------|
| **1. Visualisation** | Génération d'un échantillon Weibull (β=3, η=4), histogramme, courbe de fiabilité R(t) et taux de défaillance λ(t) |
| **2. Estimation** | Estimation de β et η par régression linéaire sur papier de Weibull |
| **3. Architecture** | Comparaison série vs parallèle sur composants exponentiels |
| **4. Maintenance** | Survie conditionnelle, espérance de vie résiduelle, politique de remplacement préventif optimal |
| **5. Processus de renouvellement** | Simulation de pannes successives, fonction M(t), trajectoires individuelles, analyse des coûts de maintenance |
| **6. Test KS** | Test de Kolmogorov-Smirnov sur les données transformées et directement sur T, comparaison avec d'autres lois |
| **7. Test Chi-deux** | Test χ² manuel et via scipy sur classes équiprobables, validation du modèle Weibull |
| **8. Analyse de sensibilité** | Impact de β et η sur R(t), E[T] et t*, carte de chaleur, indices d'élasticité |

## Stack

- Python 3.13
- `numpy`, `scipy`, `matplotlib`, `seaborn`, `pandas`
- Environnement géré avec [uv](https://docs.astral.sh/uv/)

## Lancer le projet

```bash
uv sync
jupyter notebook partie_3.ipynb
```
