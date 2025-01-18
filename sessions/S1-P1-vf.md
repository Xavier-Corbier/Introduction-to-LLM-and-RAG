# Session 1 : Introduction aux grands modèles de langage (LLMs)
## Partie 1 : Vue d'ensemble des modèles de langage
### Qu'est-ce qu'un modèle de langage ?
Un modèle de langage est un [modèle](https://developers.google.com/machine-learning/glossary?hl=fr#model) d'apprentissage automatique conçu pour prédire et générer un langage plausible. Par exemple, l'autocomplétion est un modèle de langage.

Ces modèles fonctionnent en estimant la probabilité qu'un [jeton](https://developers.google.com/machine-learning/glossary?hl=fr#token) ou une séquence de jetons apparaisse dans une séquence plus longue. Prenons la phrase suivante :

```
Quand j'entends la pluie sur mon toit, je _______ dans ma cuisine.
```

Si l'on suppose qu'un jeton est un mot, alors un modèle de langage détermine les probabilités de différents mots ou séquences de mots pour remplacer le tiret bas. Par exemple, un modèle pourrait déterminer les probabilités suivantes :

```
prépare une soupe 9,4 %
réchauffe une bouilloire 5,2 %
me recroqueville 3,6 %
fais une sieste 2,5 %
me détends 2,2 %
...
```

Une "séquence de jetons" pourrait être une phrase entière ou une série de phrases. En d'autres termes, un modèle de langage pourrait calculer la probabilité de différentes phrases ou blocs de texte entiers.

Estimer la probabilité de ce qui vient ensuite dans une séquence est utile pour de nombreuses applications : générer du texte, traduire des langues et répondre à des questions, pour n'en nommer que quelques-unes.

### Qu'est-ce qu'un grand modèle de langage ?
Modéliser le langage humain à grande échelle est une entreprise complexe et gourmande en ressources. L'évolution vers les capacités actuelles des modèles de langage et des grands modèles de langage s'est déroulée sur plusieurs décennies.

Au fur et à mesure que les modèles deviennent plus grands, leur complexité et leur efficacité augmentent. Les premiers modèles de langage pouvaient prédire la probabilité d'un mot unique ; les grands modèles modernes peuvent prédire la probabilité de phrases, de paragraphes, voire de documents entiers.

La taille et les capacités des modèles de langage ont explosé ces dernières années grâce à l'augmentation de la mémoire informatique, de la taille des jeux de données et de la puissance de traitement, ainsi qu'au développement de techniques plus efficaces pour modéliser des séquences de texte plus longues.

#### Quelle taille pour être "grand" ?
La définition est floue, mais "grand" a été utilisé pour décrire BERT (110 millions de paramètres) ainsi que PaLM 2 (jusqu'à 340 milliards de paramètres).

Les [paramètres](https://developers.google.com/machine-learning/glossary?hl=fr#parameter) sont les [poids](https://developers.google.com/machine-learning/glossary?hl=fr#weight) que le modèle a appris pendant l'entraînement, utilisés pour prédire le prochain jeton de la séquence. "Grand" peut se référer au nombre de paramètres dans le modèle ou parfois au nombre de mots dans le jeu de données.

#### Transformers
Une avancée clé dans la modélisation du langage a été l'introduction en 2017 des Transformers, une architecture basée sur l'idée de [l'attention](https://developers.google.com/machine-learning/glossary?hl=fr#attention). Cela a permis de traiter des séquences plus longues en se concentrant sur la partie la plus importante de l'entrée, résolvant les problèmes de mémoire rencontrés avec les modèles précédents.

Les Transformers sont l'architecture de pointe pour une grande variété d'applications des modèles de langage, telles que les traducteurs.

Si l'entrée est "I am a good dog.", un traducteur basé sur Transformer transforme cette entrée en sortie "Je suis un bon chien.", qui est la même phrase traduite en français.

Les Transformers complets se composent d'un encodeur et d'un décodeur. Un [encodeur](https://developers.google.com/machine-learning/glossary?hl=fr#encoder) convertit le texte d'entrée en une représentation intermédiaire, et un [décodeur](https://developers.google.com/machine-learning/glossary?hl=fr#decoder) convertit cette représentation intermédiaire en texte utile.

#### Auto-attention
Les Transformers s'appuient fortement sur un concept appelé auto-attention. La partie "auto" de l'auto-attention fait référence à la concentration "égocentrique" de chaque jeton dans un corpus. En gros, chaque jeton de l'entrée se demande : "Dans quelle mesure chaque autre jeton de l'entrée m'importe-t-il ?" Supposons que chaque jeton soit un mot et que le contexte complet soit une seule phrase. Prenons la phrase suivante :

```
L'animal n'a pas traversé la rue car il était trop fatigué.
```
Il y a 11 mots dans cette phrase, donc chacun des 11 mots prête attention aux dix autres, se demandant dans quelle mesure chacun de ces dix mots leur est pertinent. Par exemple, remarquez que la phrase contient le pronom "il". Les pronoms sont souvent ambigus. Le pronom "il" se réfère toujours à un nom récent, mais dans la phrase d'exemple, à quel nom récent "il" se réfère-t-il : à "l'animal" ou à "la rue" ?

Le mécanisme d'auto-attention détermine la pertinence de chaque mot voisin pour le pronom "il".

### Quels sont les cas d'utilisation des LLMs ?
Les LLMs sont très efficaces pour la tâche pour laquelle ils ont été conçus : générer le texte le plus plausible en réponse à une entrée. Ils commencent également à montrer de bonnes performances sur d'autres tâches, telles que la synthèse, les réponses aux questions et la classification de texte. Ce sont des [capacités émergentes](https://research.google/pubs/emergent-abilities-of-large-language-models/). Les LLMs peuvent même résoudre certains problèmes mathématiques et écrire du code (même s'il est conseillé de vérifier leur travail).

Les LLMs sont excellents pour imiter les modèles de discours humains. Entre autres, ils sont performants pour combiner des informations avec différents styles et tons.

Cependant, les LLMs peuvent être des composants de modèles qui font plus que générer du texte. Les LLMs récents ont été utilisés pour construire des détecteurs de sentiment, des classificateurs de toxicité et pour générer des légendes d'images.

### Considérations sur les LLMs
Les modèles de cette taille ne sont pas sans inconvénients.

Les plus grands LLMs sont coûteux. Leur entraînement peut prendre des mois et consommer beaucoup de ressources.

Former des modèles avec plus d'un trillion de paramètres pose des défis techniques. Une infrastructure spéciale et des techniques de programmation sont nécessaires pour coordonner le flux vers les puces et inversement.

Il existe des moyens de réduire les coûts de ces grands modèles. Deux approches sont l'inférence hors ligne et la distillation.

Les biais peuvent être un problème dans les très grands modèles et doivent être pris en compte lors de leur formation et de leur déploiement.

Comme ces modèles sont formés sur le langage humain, cela peut introduire de nombreux problèmes éthiques potentiels, notamment l'utilisation abusive du langage et les biais liés à la race, au genre, à la religion, etc.

Il est clair qu'à mesure que ces modèles continuent de grandir et de s'améliorer, il est essentiel de rester vigilant quant à la compréhension et à l'atténuation de leurs inconvénients.

### Temps de quiz !

Le quiz est disponible sur Wooclap. Cependant, vous pouvez déjà consulter les questions.

1. **Quelle est la fonction principale d'un modèle de langage ?**
   - a) Créer de nouveaux mots pour une langue.
   - b) Prédire et générer des séquences de langage plausibles.
   - c) Corriger la grammaire dans un texte.
   - d) Augmenter la vitesse de frappe sur un clavier.

2. **Quelle avancée significative dans les modèles de langage a été introduite en 2017, et quelle est sa caractéristique principale ?**
   - a) Réseaux LSTM, axés sur les cellules de mémoire.
   - b) CNN, axés sur les relations spatiales.
   - c) Transformers, axés sur les mécanismes d'attention.
   - d) RNN, axés sur le traitement des données séquentielles.

3. **Quelles sont certaines des capacités émergentes des grands modèles de langage (LLMs) en dehors de la génération de texte ?**
   - a) Résoudre des problèmes mathématiques et écrire du code.
   - b) Jouer à des jeux vidéo.
   - c) Concevoir automatiquement des sites web.
   - d) Mener des entretiens.