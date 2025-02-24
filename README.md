# CIFAR-100 Classification

Ce repository contient le code pour l'entraînement de modèles de classification sur le dataset **CIFAR-100** en utilisant différentes architectures de réseaux de neurones profonds et techniques d'amélioration.

## Structure du Repository

Le projet est organisé en plusieurs branches, chacune correspondant à une approche ou architecture spécifique :

- **Xtension** : Expérimentation avec un modèle basé sur Xtension.
- **ResNet** : Implémentation et entraînement d'un modèle ResNet adapté à CIFAR-100.
- **main** : Contient le **meilleur modèle** obtenu en termes de performance sur le dataset de test.

### Organisation des Fichiers

- **cifar-100-python/** : Contient les fichiers du dataset CIFAR-100.
- **main.ipynb** : Notebook principal pour entraîner les modèles.
- **README.md** : Ce fichier, qui explique le projet et son utilisation.
- **requirements.txt** : Liste des dépendances nécessaires pour exécuter le projet.

## Modèles et Techniques Utilisées

### Architectures de Base

Les modèles ont été entraînés avec des architectures reconnues pour leur efficacité en classification d'images, notamment **ResNet** et **Xtension**.

### Callbacks et Techniques d'Amélioration

Pour améliorer l'entraînement, plusieurs callbacks classiques ont été utilisés :

- **ModelCheckpoint** : Sauvegarde le meilleur modèle pendant l'entraînement.
- **ReduceLROnPlateau** : Réduit le taux d'apprentissage lorsque la performance sur la validation stagne.
- **EarlyStopping** : Interrompt l'entraînement en cas d'absence de progrès sur la validation.
- **HardExampleMining** : (Technique initiale) Identifie et met l'accent sur les exemples d'entraînement avec les plus grandes pertes (crossentropy catégorique).

**Nouvelle Technique**  
Afin d'augmenter significativement l'accuracy, une nouvelle stratégie a été testée : le **redimensionnement des images**. Cette approche a permis d'améliorer l'accuracy sur le dataset de test de **50% à 78%**.

> Note : La combinaison de la technique de redimensionnement avec l'entraînement sur des images à données plus complexes n'a pas pu être réalisée en raison des limitations de mémoire CPU sur la machine utilisée.

## Résultats et Visualisation

Les performances des modèles sont évaluées à la fin de l'entraînement :

- **Avant redimensionnement** : ~50% d'accuracy sur le dataset de test.
- **Après redimensionnement** : ~78% d'accuracy sur le dataset de test.

Les résultats détaillés et visualisations sont générés dans le notebook principal.

## Installation et Exécution

### Prérequis

Assurez-vous d'avoir Python 3.9.13 (ou version ultérieure) ainsi que les bibliothèques listées dans **requirements.txt** installées :

```bash
pip install -r requirements.txt
```

### Entraînement du Modèle

Pour lancer l'entraînement, exécutez le notebook **main.ipynb** dans l'ordre indiqué.

