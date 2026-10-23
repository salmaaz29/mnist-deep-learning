# Deep Learning – Classification d'images

## Présentation de l'atelier

Pour objectif d'étudier et de comparer différentes architectures de réseaux de neurones appliquées à la classification d'images.

Les expérimentations sont réalisées sur le jeu de données **MNIST**, qui contient des images de chiffres manuscrits allant de 0 à 9.

Ce travail est organisé en deux parties :
- **Partie 1 :** Étude et expérimentation de différentes architectures de Deep Learning.
- **Partie 2 :** Exploration du transfert d'apprentissage (*Transfer Learning*) et du fine-tuning à travers des modèles préentraînés.

## Structure du projet

```text
mnist-deep-learning/
│
├── README.md
│
├── atelier-2-partie1.ipynb
│
└── partie2_atelier2.ipynb
```

*Remarque : les noms des notebooks sont donnés à titre d'exemple. Il faut les adapter aux noms réels de tes fichiers.*

## Jeu de données : MNIST

Le jeu de données MNIST est utilisé pour entraîner et évaluer les différents modèles.

Il contient :
- 60 000 images pour l'entraînement.
- 10 000 images pour le test.
- Des images en niveaux de gris de dimensions 28 × 28 pixels.
- 10 classes correspondant aux chiffres de 0 à 9.

## Partie 1 – Étude des architectures de Deep Learning

Cette première partie consiste à implémenter, entraîner et évaluer différentes architectures pour la reconnaissance des chiffres manuscrits.

### Modèles étudiés

**1. CNN (Convolutional Neural Network)**

Un réseau de neurones convolutif permettant d'extraire automatiquement les caractéristiques spatiales des images grâce aux couches de convolution et de pooling.

**2. ViT (Vision Transformer)**

Une architecture basée sur les Transformers, qui traite les images sous forme de séquences de patches afin d'effectuer la classification.

**3. Faster R-CNN**

Une architecture initialement conçue pour la détection d'objets, expérimentée dans le cadre de la reconnaissance des chiffres manuscrits.

## Partie 2 – Transfert d'apprentissage et Fine-Tuning

Cette deuxième partie porte sur l'utilisation de modèles préentraînés afin de les adapter à une nouvelle tâche de classification.

### Modèles étudiés

**1. AlexNet**

Un réseau de neurones convolutif préentraîné, adapté à la classification des chiffres manuscrits grâce au fine-tuning.

**2. VGG16**

Un réseau de neurones convolutif profond préentraîné, également adapté au jeu de données MNIST par transfert d'apprentissage.

### Prétraitement des images

Les modèles AlexNet et VGG16 nécessitent des images de dimensions et de formats différents de ceux du jeu de données MNIST.

Un prétraitement est donc appliqué :
- Redimensionnement des images de 28 × 28 à 224 × 224 pixels.
- Conversion des images en niveaux de gris vers trois canaux.
- Normalisation des images à l'aide des statistiques du jeu de données ImageNet.

## Résultats expérimentaux

Le tableau suivant présente les performances obtenues par les différents modèles lors des expérimentations.

| Modèle | Accuracy | F1-score pondéré | Test Loss |
|---|---:|---:|---:|
| CNN | 99,17 % | 0,9917 | 0,0233 |
| ViT | 86,41 % | 0,8627 | 0,4141 |
| Faster R-CNN | 96,60 % | 0,9661 | Non calculée |
| AlexNet | 97,41 % | 0,9741 | 0,0873 |
| VGG16 | 97,72 % | 0,9772 | 0,0683 |

**Remarque :** les modèles n'ont pas tous été évalués sur le même nombre d'images :
- CNN et ViT : 10 000 images.
- Faster R-CNN : 4 000 images.
- AlexNet et VGG16 : 3 200 images.

La comparaison des performances reste donc indicative et les résultats ne sont pas issus d'une évaluation strictement identique.

## Métriques d'évaluation

Pour mesurer les performances des modèles, plusieurs métriques sont utilisées :

- **Accuracy (Exactitude) :** proportion des prédictions correctement classées.
- **Precision (Précision) :** proportion des prédictions positives qui sont correctes.
- **Recall (Rappel) :** capacité du modèle à identifier correctement les exemples d'une classe.
- **F1-score :** moyenne harmonique entre la précision et le rappel.
- **Loss :** mesure de l'erreur entre les prédictions du modèle et les valeurs réelles.

Des matrices de confusion et des courbes d'apprentissage peuvent également être utilisées pour analyser les performances et les erreurs de classification.

## Analyse et comparaison des résultats

Les expérimentations permettent de mettre en évidence plusieurs observations :

- Le CNN obtient la meilleure performance avec une accuracy de 99,17 %.
- VGG16 et AlexNet présentent également de très bonnes performances grâce au transfert d'apprentissage et au fine-tuning.
- Le modèle ViT obtient une accuracy de 86,41 %, inférieure à celle des autres modèles dans les conditions de cette expérimentation.
- Faster R-CNN atteint une accuracy de 96,60 %, mais présente un temps d'entraînement particulièrement élevé.

Ces résultats montrent que les performances dépendent notamment de l'architecture choisie, du prétraitement des données et des paramètres d'entraînement.

## Technologies et bibliothèques utilisées

- Python
- PyTorch
- TorchVision
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Kaggle

## Compétences acquises

À travers ce travail pratique, nous avons pu :

- Comprendre les principes fondamentaux du Deep Learning et de la classification d'images.
- Implémenter et entraîner différentes architectures de réseaux de neurones.
- Découvrir les réseaux convolutifs (CNN) et les architectures basées sur les Transformers.
- Comprendre le fonctionnement du transfert d'apprentissage et du fine-tuning.
- Effectuer le prétraitement des images selon les exigences des modèles.
- Évaluer les performances à l'aide de différentes métriques.
