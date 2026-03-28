# Projet Statistiques — Fiabilité & Maintenance Industrielle

Analyse statistique complète de la fiabilité d'un parc de 1 000 serveurs industriels,
avec identification du modèle probabiliste, estimation des paramètres, validation,
optimisation de la maintenance et modélisation markovienne.

## Contenu du notebook

| Partie                             | Description                                                                                                                                                                                                                              |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Identification du modèle**    | Génération d'un échantillon Weibull (β=3, η=4, n=1000, seed=42) · Histogramme avec densité théorique · Fiabilité empirique R̂(t) · Taux de défaillance λ̂(t) par KDE (règle de Scott)                                                      |
| **2. Estimation des paramètres**   | Régression linéaire OLS sur papier de Weibull (formule de Hazen) · MLE via scipy avec matrice de Fisher et intervalles de confiance à 95 % · Comparaison OLS vs MLE                                                                      |
| **3. Tests d'adéquation**          | Test du chi-deux sur 20 classes équiprobables · Test de Kolmogorov-Smirnov · QQ-plot de validation visuelle                                                                                                                              |
| **4. Processus de renouvellement** | Simulation de 1 000 trajectoires sur 20 000 h · Fonction de renouvellement M(t) · Théorème élémentaire (convergence vers t/E[T]) · Trajectoires individuelles                                                                            |
| **5. Politique de maintenance**    | Modèle de coût C(τ) (Barlow-Proschan, 1965) · Optimisation par brentq (condition du 1er ordre) · τ\* ≈ 1 485 h, gain 63,6 % vs politique corrective · Analyse de sensibilité et élasticités S*β, S*η                                     |
| **6. Modélisation markovienne**    | **Piste 1** : CDM 2 états non-homogène, équations de Chapman-Kolmogorov, pont avec Weibull (μ=0) · **Piste 2** : approximation Erlang (m=7 phases), distribution stationnaire πQ=0, disponibilité asymptotique A∞(μ), μ\* pour A∞ ≥ 90 % |

## Résultats clés

| Grandeur                    | Valeur                            |
| --------------------------- | --------------------------------- |
| β̂ MLE                       | 2,971 — IC 95 % : [2,827 ; 3,115] |
| η̂ MLE (×10³ h)              | 3,958 — IC 95 % : [3,871 ; 4,044] |
| χ²_obs / p-valeur           | 22,96 / 0,151 → H₀ non rejetée    |
| D_n KS / p-valeur           | 0,0219 / 0,716 → H₀ non rejetée   |
| τ\* remplacement préventif  | 1 485 h ≈ 62 jours                |
| Gain préventif vs correctif | 63,6 %                            |
| μ\* (A∞ ≥ 90 %, Piste 2)    | 2,57 milliers h⁻¹ → MTTR ≤ 389 h  |

## Stack

- Python 3.13
- `numpy`, `scipy`, `matplotlib`
- Environnement géré avec [uv](https://docs.astral.sh/uv/)

## Lancer le projet

```bash
uv sync
jupyter notebook partie_3.ipynb
```
