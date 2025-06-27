# Heart Disease Classification 🫀🔬

Prototype de machine-learning visant à prédire la présence d’une maladie cardiaque à partir de paramètres cliniques de base (âge, tension artérielle, cholestérol, fréquence cardiaque, etc.).
Basé sur le jeu de données **Cleveland Heart Disease** de l’UCI.

---

## Sommaire

1. [Objectifs](#objectifs)
2. [Jeu de données](#jeu-de-données)
3. [Structure du dépôt](#structure-du-dépôt)
4. [Installation rapide](#installation-rapide)
5. [Guide d’utilisation](#guide-dutilisation)
6. [Résultats obtenus](#résultats-obtenus)
7. [Feuille de route / TODO](#feuille-de-route--todo)
8. [Contribuer](#contribuer)
9. [Licence](#licence)
10. [Remerciements](#remerciements)

---

## Objectifs

* **Détection précoce** : atteindre ≥ 95 % de précision pour un dépistage rapide.
* **Comparaison de modèles** : Logistic Regression, K-NN, Random Forest & autres (Scikit-Learn).
* **Explicabilité** : identifier les facteurs de risque via l’importance des variables.
* **Reproductibilité** : tout le workflow est contenu dans un notebook unique.

---

## Jeu de données

| Source                                      | Taille   | Cible                                |
| ------------------------------------------- | -------- | ------------------------------------ |
| UCI ML Repository – Cleveland Heart Disease | 303 × 14 | `target` (0 = absence, 1 = présence) |

Le fichier CSV d’origine (`heart-disease (1).csv`) est déjà présent ; aucun téléchargement externe requis.

---

## Structure du dépôt

```
.
├── heart-disease-classification.ipynb   # Notebook complet (EDA → Modélisation → Évaluation)
├── heart-disease (1).csv               # Données brutes
├── environment.yml                     # Dépendances Conda
└── .gitignore
```

---

## Installation rapide

> **Pré-requis :** Python ≥ 3.11 **ou** Conda ≥ 23.x

```bash
# 1. Cloner le repo
git clone https://github.com/Lucas97450/heart_disease_classification.git
cd heart_disease_classification

# 2. Créer l’environnement
conda env create -f environment.yml
conda activate heart_disease_classification

# 3. Lancer Jupyter
jupyter lab     # puis ouvrir le notebook
```

> *Astuce :* en cas d’erreur Conda, créez un `requirements.txt` avec
> `conda list --export > requirements.txt` puis `pip install -r requirements.txt`.

---

## Guide d’utilisation

1. **EDA** : exécuter les premières cellules pour l’aperçu des données et la heatmap de corrélation.
2. **Pré-traitement** : scaling, train/test split, encodage si nécessaire.
3. **Entraînement** : comparer les performances des modèles (GridSearchCV optionnel).
4. **Évaluation** : matrice de confusion, classification report, courbes ROC/AUC, features importance.
5. **Export (optionnel)** : sauvegarder le meilleur modèle avec `joblib.dump` pour une future API Flask/Streamlit.

---

## Résultats obtenus

| Modèle              | Accuracy CV (5-fold) | Recall   | F1-Score |
| ------------------- | -------------------- | -------- | -------- |
| Logistic Regression | ≈ 85 %               | 0.86     | 0.85     |
| K-Nearest Neighbors | ≈ 82 %               | 0.80     | 0.81     |
| **Random Forest**   | **≈ 88 %**           | **0.90** | **0.88** |

Les scores exacts peuvent varier selon la graine aléatoire.

---

## Feuille de route / TODO

| Étape                                 | Statut | Amélioration prévue                                             |
| ------------------------------------- | ------ | --------------------------------------------------------------- |
| Nettoyage `environment.yml`           | 🔄     | Reformater en YAML propre                                       |
| Export du meilleur modèle (`.joblib`) | ⬜      | Ajouter une cellule dédiée                                      |
| API REST (FastAPI/Flask)              | ⬜      | Endpoint `POST /predict`                                        |
| Dashboard Streamlit                   | ⬜      | Interface utilisateur pour charger un CSV ou saisir les valeurs |

---

## Contribuer

1. **Fork** puis `git checkout -b feature/ma-feature`.
2. Commit (`git commit -m "Ajout …"`).
3. Push (`git push origin feature/ma-feature`) et ouvrez une **Pull Request**.
4. Merci d’exécuter `pre-commit` avant de soumettre (PEP 8).

---

## Licence

Distribué sous licence **MIT** – ajoutez le fichier `LICENSE` le cas échéant.

---

## Remerciements

* Jeu de données original : UCI Machine Learning Repository.
* Inspiration notebook : *Zero to Mastery – Machine Learning Engineer*.
* Icônes : [Twemoji](https://twemoji.twitter.com/) (CC-BY 4.0).

---

*Made with ❤️ by Lucas & Contributors*
