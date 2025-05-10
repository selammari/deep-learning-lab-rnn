# ?? Deep Learning Lab – Analyse de sentiment avec RNN, GRU et LSTM

## ?? Objectif du projet

L’objectif de ce projet est de mettre en œuvre et comparer trois architectures de réseaux de neurones récurrents — **RNN**, **GRU** et **LSTM** — dans une tâche de classification de texte.  
Nous utilisons le **dataset IMDb**, contenant des critiques de films annotées comme positives ou négatives, pour entraîner nos modèles à effectuer une **analyse de sentiments**.

---

## ?? Données utilisées

Le dataset **IMDb** (Internet Movie Database) est une base de données de critiques de films, largement utilisée dans les tâches de NLP (Natural Language Processing).

- **Nombre total d’échantillons** : 50 000 critiques
- **Répartition** : 25 000 pour l'entraînement, 25 000 pour les tests
- **Classes** : 
  - `1` = critique positive  
  - `0` = critique négative

Les critiques sont pré-traitées : mises en minuscules, ponctuation supprimée, puis tokenisées.

---

## ?? Explication des modèles

### ?? RNN – Recurrent Neural Network

Les RNN traitent les séquences mot par mot et utilisent une mémoire interne pour tenir compte des états précédents. Ils peuvent capturer la dépendance temporelle entre les mots.  
**Limite** : ils ont du mal à retenir les informations sur de longues séquences à cause du **vanishing gradient**.

---

### ?? GRU – Gated Recurrent Unit

Le GRU est une version optimisée du RNN, qui résout en partie le problème du vanishing gradient. Il utilise :
- **Porte de mise à jour** : décide de conserver ou d’oublier les informations
- **Porte de réinitialisation** : détermine l’influence de l’état précédent

Avantage : plus rapide à entraîner que LSTM, avec souvent des performances similaires.

---

### ?? LSTM – Long Short-Term Memory

Le LSTM est une architecture plus complexe, avec trois portes :
- **Porte d’entrée** : quelles nouvelles informations stocker
- **Porte d’oubli** : quelles anciennes informations oublier
- **Porte de sortie** : quelle information transférer à l’état suivant

Il est particulièrement bon pour gérer des **longues dépendances** dans le texte.

---

## ?? Détails des modèles implémentés

Les trois architectures suivent une structure commune :
- **Embedding layer** : convertit les mots en vecteurs denses
- **RNN / GRU / LSTM layer**
- **Fully connected layer (linéaire)** : produit la sortie (0 ou 1)
- **Activation sigmoid** pour obtenir une probabilité
- **Fonction de perte** : `Binary Cross Entropy`
- **Optimiseur** : `Adam`

Chaque modèle est entraîné pendant plusieurs époques et évalué en termes d'**accuracy** et de **loss** sur un jeu de test.

---

## ?? Environnement de développement

### ?? Outils et bibliothèques utilisés
- Python 3.10
- PyTorch 2.x / TensorFlow 2.x
- Jupyter Notebook
- Numpy, Matplotlib, Seaborn
- Hugging Face Datasets (optionnel)

### ?? Installation rapide

Créer un environnement virtuel (optionnel) :
```bash
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate sous Windows


[Voir la vidéo explicative]https://drive.google.com/file/d/1ULthKPbOutVzxy-IZ7us0AocKTupBYXa/view?usp=drive_link

