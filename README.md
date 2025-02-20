# CIFAR-100 Classification

Ce repository contient le code pour l'entraînement de modèles de classification sur le dataset **CIFAR-100** en utilisant différentes architectures de réseaux de neurones profonds.

## Structure du repository

Le projet est structuré en plusieurs branches, chacune correspondant à une architecture de base différente :

- **Xtension** : Expérimentation avec un modèle basé sur Xtension.
- **ResNet** : Implémentation et entraînement d'un modèle ResNet adapté à CIFAR-100.
- **main** : Contient le **meilleur modèle** obtenu en termes de performance sur le dataset de test.

### Organisation des fichiers

- **cifar-100-python/** : Contient les fichiers du dataset CIFAR-100.
- **main.ipynb** : Notebook principal pour entraîner les modèles.
- **README.md** : Ce fichier, expliquant le projet et son utilisation.
- **requirements.txt** : Contient la liste des dépendances nécessaires pour exécuter le projet.

## Modèles et techniques utilisées

### Base Models

Les modèles ont été entraînés avec des architectures connues pour leur efficacité sur les tâches de classification d'images, notamment **ResNet** et **Xtension**.

### Callbacks Utilisés

En plus des callbacks classiques pour l'amélioration de l'entraînement, un **callback personnalisé "HardExampleMining"** a été ajouté :

- **ModelCheckpoint** : Sauvegarde le meilleur modèle au cours de l'entraînement.
- **ReduceLROnPlateau** : Réduit le taux d'apprentissage lorsque la validation ne s'améliore plus.
- **EarlyStopping** : Arrête l'entraînement si la validation ne progresse plus.
- **HardExampleMining** : Identifie les exemples d'entraînement ayant les plus grandes pertes (*categorical crossentropy*) et leur attribue un poids plus important dans la mise à jour des gradients. Cette technique a été implémentée d'après une recherche indiquant son efficacité pour améliorer les performances.

## Amélioration des performances

L'ajout du callback **HardExampleMining** a permis une nette amélioration de l'accuracy sur le dataset de test :

- Avant : **50%** d'accuracy
- Après : **55%** d'accuracy

## Installation et Exécution

### Prérequis

Assurez-vous d'avoir Python 3.9.13 installé avec les bibliothèques suivantes :

```bash
pip install -r requirements.txt
```

### Entraînement du modèle

Pour entraîner un modèle, exécutez le notebook dans l'ordre

## Résultats et Visualisation

Les performances des modèles sont disponibles a la fin de l'entrainement


