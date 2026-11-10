# Accidentologie routière en Tunisie (2002–2026)

Analyse exploratoire et statistique de **199 316 accidents de la route** enregistrés en Tunisie entre 2002 et septembre 2026 : où, quand, pourquoi, et surtout **qu'est-ce qui rend un accident mortel**.

## Contenu

| Fichier | Rôle |
|---|---|
| `analyse_accidentologie_tunisie.ipynb` | Notebook complet (nettoyage → analyse → tests → modèle), exécuté |
| `data/accidents_routiers_tunisie.xlsx` | Données brutes (colonnes en arabe) |
| `figures/` | Les 10 graphiques produits par le notebook |
| `outputs/indicateurs_accidentologie.xlsx` | Tableaux d'indicateurs (gouvernorats, causes, heures, modèle…) |

## Démarche

1. **Qualité des données** : valeurs manquantes (délégation absente pour 83 % des accidents, renseignée de façon systématique seulement depuis 2021), codes sentinelles du point kilométrique, jours de la semaine incohérents avec la date, année 2026 incomplète.
2. **Nettoyage** : harmonisation de l'arabe, traduction en français (gouvernorats, causes, autorité), regroupement de 1 930 libellés de type en 7 catégories de collision.
3. **Analyse descriptive** : gouvernorats et délégations, évolution annuelle, mois / jour / heure (accidents **par jour** pour comparer des mois de longueurs différentes), causes, types de collision, victimes.
4. **Tests statistiques** : khi-deux et V de Cramér, Mann-Whitney et Kruskal-Wallis avec tailles d'effet, corrélations de Spearman.
5. **Modèle** : régression logistique de la probabilité qu'un accident soit mortel (AUC 0,74), rapports de cotes et intervalles de confiance.

## Principaux résultats

- Le nombre d'accidents a baissé de 55 % entre 2002 et 2025, mais celui des tués de 21 % seulement : la part d'accidents mortels est passée de 11,5 % à 20,5 %.
- Les accidents sont concentrés dans le Grand Tunis et sur le littoral, mais ils sont **plus graves dans l'intérieur et le Sud** (27,6 % de mortels à Médenine contre 7 % à Tunis).
- La nuit (0 h–6 h), entre un quart et un tiers des accidents sont mortels, contre 11 % en journée.
- À circonstances égales, la gravité est surtout liée au **réseau routier** (garde nationale, OR ≈ 2,5), à la **vitesse** (OR ≈ 2,5), à la **nuit** (OR ≈ 2,3) et aux **piétons** (OR ≈ 1,7).

## Lancer le projet

```bash
pip install -r requirements.txt
jupyter notebook analyse_accidentologie_tunisie.ipynb
```

## Auteur

Mohamed Aziz Ameur — [github.com/mohamedazizameur-ai](https://github.com/mohamedazizameur-ai)
