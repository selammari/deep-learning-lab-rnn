# ?? Deep Learning Lab � Analyse de sentiment avec RNN, GRU et LSTM

## ?? Objectif du projet

L�objectif de ce projet est de mettre en �uvre et comparer trois architectures de r�seaux de neurones r�currents � **RNN**, **GRU** et **LSTM** � dans une t�che de classification de texte.  
Nous utilisons le **dataset IMDb**, contenant des critiques de films annot�es comme positives ou n�gatives, pour entra�ner nos mod�les � effectuer une **analyse de sentiments**.

---

## ?? Donn�es utilis�es

Le dataset **IMDb** (Internet Movie Database) est une base de donn�es de critiques de films, largement utilis�e dans les t�ches de NLP (Natural Language Processing).

- **Nombre total d��chantillons** : 50 000 critiques
- **R�partition** : 25 000 pour l'entra�nement, 25 000 pour les tests
- **Classes** : 
  - `1` = critique positive  
  - `0` = critique n�gative

Les critiques sont pr�-trait�es : mises en minuscules, ponctuation supprim�e, puis tokenis�es.

---

## ?? Explication des mod�les

### ?? RNN � Recurrent Neural Network

Les RNN traitent les s�quences mot par mot et utilisent une m�moire interne pour tenir compte des �tats pr�c�dents. Ils peuvent capturer la d�pendance temporelle entre les mots.  
**Limite** : ils ont du mal � retenir les informations sur de longues s�quences � cause du **vanishing gradient**.

---

### ?? GRU � Gated Recurrent Unit

Le GRU est une version optimis�e du RNN, qui r�sout en partie le probl�me du vanishing gradient. Il utilise :
- **Porte de mise � jour** : d�cide de conserver ou d�oublier les informations
- **Porte de r�initialisation** : d�termine l�influence de l��tat pr�c�dent

Avantage : plus rapide � entra�ner que LSTM, avec souvent des performances similaires.

---

### ?? LSTM � Long Short-Term Memory

Le LSTM est une architecture plus complexe, avec trois portes :
- **Porte d�entr�e** : quelles nouvelles informations stocker
- **Porte d�oubli** : quelles anciennes informations oublier
- **Porte de sortie** : quelle information transf�rer � l��tat suivant

Il est particuli�rement bon pour g�rer des **longues d�pendances** dans le texte.

---

## ?? D�tails des mod�les impl�ment�s

Les trois architectures suivent une structure commune :
- **Embedding layer** : convertit les mots en vecteurs denses
- **RNN / GRU / LSTM layer**
- **Fully connected layer (lin�aire)** : produit la sortie (0 ou 1)
- **Activation sigmoid** pour obtenir une probabilit�
- **Fonction de perte** : `Binary Cross Entropy`
- **Optimiseur** : `Adam`

Chaque mod�le est entra�n� pendant plusieurs �poques et �valu� en termes d'**accuracy** et de **loss** sur un jeu de test.

---

## ?? Environnement de d�veloppement

### ?? Outils et biblioth�ques utilis�s
- Python 3.10
- PyTorch 2.x / TensorFlow 2.x
- Jupyter Notebook
- Numpy, Matplotlib, Seaborn
- Hugging Face Datasets (optionnel)

### ?? Installation rapide

Cr�er un environnement virtuel (optionnel) :
```bash
python -m venv venv
source venv/bin/activate  # ou venv\Scripts\activate sous Windows


[Voir la vid�o explicative]https://drive.google.com/file/d/1ULthKPbOutVzxy-IZ7us0AocKTupBYXa/view?usp=drive_link

