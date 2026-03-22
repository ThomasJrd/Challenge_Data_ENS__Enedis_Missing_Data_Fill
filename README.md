# ⚡ Enedis Data Challenge : Reconstruction de Courbes de Consommation

Ce dépôt contient ma solution pour le challenge de reconstruction de données manquantes sur des courbes de consommation électrique synthétiques (générées par *DeepCourbogen*), dans le cadre du mécanisme d'ajustement d'Enedis.

## 📌 Contexte du Projet
Le compteur Linky est déployé chez plus de 38 millions de clients. Pour assurer l'équilibre offre/demande sur le marché électrique français, Enedis doit traiter des masses de données de consommation. 

Cependant, la transmission de ces données peut subir des problèmes techniques, créant des "trous". Pour respecter le **RGPD**, Enedis développe des algorithmes de complétion (imputation) sur des données synthétiques haute fidélité.

**Objectif :** Reconstruire les données manquantes de 1 000 courbes cibles (`holed_`) en utilisant les informations des milliers d'autres courbes complètes du dataset.

---

## 📊 Données & Métrique
* **Dataset d'entraînement :** DataFrame de 21 000 colonnes (consommation en Watts).
* **Challenge :** Compléter les 1 000 dernières colonnes (`holed_X`).
* **Métrique d'évaluation :** Erreur Absolue Moyenne (MAE) :
  - La moyenne des erreurs absolues ramenée au nombre réel de valeurs manquantes.

---

## 🛠️ Méthodes Explorées
Dans ce projet, j'ai testé plusieurs approches pour dépasser le benchmark d'interpolation linéaire :

* **K-Nearest Neighbors (k-NN) :** Recherche de courbes similaires dans le dataset pour imputer les valeurs manquantes.
* **Feature Engineering (TSFresh) :** Extraction de caractéristiques temporelles pour capturer la saisonnalité et les pics de consommation.
* **Moyenne Mobile Simple (SMA) :** Exploration de méthodes de lissage pour la complétion des séries temporelles.
* **Machine Learning Automatisé :** Utilisation de `getml` pour la création automatique de features relationnelles.

---

## 🚀 Installation & Utilisation

### Prérequis
* Python 3.9+
* Jupyter Notebook

### Installation
1. Clonez le dépôt :
   ```bash
   git clone [https://github.com/ThomasJrd/VotreDepot.git](https://github.com/ThomasJrd/VotreDepot.git)
   cd VotreDepot
