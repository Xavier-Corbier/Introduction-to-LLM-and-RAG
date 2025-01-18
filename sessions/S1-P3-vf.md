# Session 1 : Introduction aux grands modèles de langage (LLMs)
## Partie 3 : Considérations sur la sécurité et l'équité pour les modèles génératifs

### Introduction
Le développement rapide de l'IA générative a permis de lancer des fonctionnalités et des produits en des délais relativement courts. Les équipes qui mettent sur le marché des produits dotés de capacités d'IA générative doivent veiller à offrir des expériences utilisateur de haute qualité, sûres, équitables et inclusives, conformément aux [principes de l'IA](https://ai.google/responsibility/principles/).

Une approche responsable des applications génératives devrait prévoir des plans pour accomplir les points suivants :
- Politiques de contenu, analyse des risques et des dommages potentiels
- Génération responsable
- Prévention des préjudices
- Évaluation et tests adverses

### Politiques de contenu, analyse des risques et des dommages potentiels
Les politiques de contenu ne sont qu'une étape dans la prévention des préjudices pour les utilisateurs. Il est également important de définir des objectifs et des principes directeurs pour la qualité, la sécurité, l'équité et l'inclusion.

#### Qualité
Les équipes doivent élaborer des stratégies pour répondre aux requêtes dans des domaines sensibles tels que l'information médicale, afin de fournir des expériences utilisateur de haute qualité. Les stratégies responsables incluent la présentation de points de vue multiples, l'évitement de sujets sans preuves scientifiques, ou la fourniture d'informations factuelles avec attribution.

#### Sécurité
Les mesures de sécurité de l'IA visent à prévenir ou contenir les actions susceptibles de causer un préjudice, intentionnellement ou non. Sans des mesures d'atténuation appropriées, les modèles génératifs peuvent produire des contenus non sûrs qui violent les politiques de contenu ou causent un inconfort aux utilisateurs. Par exemple, fournir des explications aux utilisateurs si une sortie a été bloquée ou si le modèle n'a pas pu produire une réponse acceptable.

#### Équité et inclusion
Assurez-vous de la diversité dans une réponse et entre plusieurs réponses à la même question. Par exemple, une réponse à une question sur les musiciens célèbres ne devrait pas inclure uniquement des noms ou images de personnes ayant la même identité de genre ou la même couleur de peau. Les équipes doivent s'efforcer de fournir du contenu adapté à différentes communautés lorsqu'il est demandé. Examinez les données d'entraînement pour la diversité et la représentation des identités, cultures et démographies multiples. Évitez les stéréotypes communs, comme associer des métiers "féminins" ou "masculins" de manière stéréotypée.

#### Analyse des risques et des dommages potentiels
Les étapes suivantes sont recommandées pour construire des applications basées sur des LLMs :
- Comprendre les risques de sécurité liés à votre application
- Envisager des ajustements pour atténuer ces risques
- Effectuer des tests de sécurité adaptés à votre cas d'usage
- Recueillir les retours des utilisateurs et surveiller l'utilisation

### Génération responsable
#### Sécurité intégrée dans le modèle
Par exemple, l'API PaLM inclut des paramètres de sécurité réglables qui bloquent les contenus potentiellement non sûrs dans six catégories : dérogatoire, toxique, sexuel, violent, dangereux et médical. Ces paramètres permettent aux développeurs d'ajuster ce qui est approprié à leurs cas d'usage tout en maintenant des protections intégrées contre les principaux préjudices (comme la mise en danger des enfants), qui sont toujours bloquées.

#### Ajustement du modèle
Le réglage fin d'un modèle peut lui apprendre à répondre en fonction des besoins de l'application. Des exemples de questions et de réponses sont utilisés pour enseigner au modèle comment mieux répondre à de nouveaux cas d'usage, traiter des types de préjudices ou appliquer différentes stratégies souhaitées dans les réponses.

Exemples :
- Ajuster les sorties pour mieux correspondre au contexte de votre application.
- Fournir une méthode d'entrée facilitant des sorties plus sûres (par exemple, restreindre les entrées à une liste déroulante).
- Bloquer les entrées non sûres et filtrer les sorties avant de les montrer à l'utilisateur.

#### Prévention des préjudices
D'autres méthodes de prévention incluent l'utilisation de classificateurs entraînés pour étiqueter chaque requête avec des signaux de préjudices potentiels ou adverses. De plus, vous pouvez limiter les requêtes d'un même utilisateur dans une période donnée pour éviter un usage abusif, ou vous protéger contre des injections de prompts malveillants.

Des garde-fous peuvent également être placés sur les sorties. Par exemple, des garde-fous de modération de contenu, comme des classificateurs, peuvent détecter les contenus violant les politiques. Si des signaux déterminent que la sortie est nuisible, l'application peut fournir une réponse d'erreur, une réponse vide ou une sortie pré-écrite.

#### Évaluation, métriques et tests
Les produits d'IA générative doivent être rigoureusement évalués pour s'assurer qu'ils respectent les politiques de sécurité et les principes directeurs avant leur lancement. Pour établir une base d'évaluation et mesurer les améliorations dans le temps, des métriques doivent être définies pour chaque dimension importante de la qualité du contenu.

Exemples de métriques :
- **Repères de sécurité** : Concevoir des métriques reflétant les façons dont l'application pourrait être non sûre, et tester les performances à l'aide de jeux de données d'évaluation.
- **Taux de violation** : Nombre de sorties violant les politiques, mesuré sur un jeu de données adversarial équilibré.
- **Taux de réponse vide** : Nombre de réponses vides données à un jeu de requêtes équilibré.
- **Diversité** : Diversité des attributs d'identité dans les réponses générées.
- **Équité** : Capacité à fournir la même qualité de service pour des requêtes contre-factuelles d'attributs sensibles.

##### Tests adverses
Les tests adverses visent à "casser" votre application pour identifier ses points faibles et y remédier.

Les tests adverses consistent à évaluer systématiquement un modèle avec des entrées malveillantes ou potentiellement nuisibles :
- Une entrée malveillante est conçue pour produire un résultat dangereux ou nuisible (ex. : demander à un modèle de texte de produire un discours haineux).
- Une entrée involontairement nuisible peut sembler innocente, mais produit un résultat préjudiciable (ex. : demander à décrire une personne d'une ethnie particulière et recevoir un résultat raciste).

Les tests adverses suivent un workflow similaire à une évaluation standard :
1. Trouver ou créer un jeu de données de test
2. Effectuer une inférence du modèle
3. Annoter les sorties
4. Analyser et rapporter les résultats

Les données de test adverses doivent inclure des cas rares, des exemples inhabituels et des cas limites pertinents pour les politiques de sécurité.

### Temps de quiz !

1. **Quel est l'objectif principal des politiques de contenu dans le contexte de l'IA générative ?**  
   - a) Augmenter la vitesse d'entraînement des modèles.  
   - b) Prévenir les préjudices pour les utilisateurs et garantir qualité, sécurité, équité et inclusion.  
   - c) Réduire les coûts informatiques.  
   - d) Se concentrer sur l'amélioration de l'interface graphique des applications.

2. **Quel est un exemple de fonctionnalité de sécurité intégrée dans l'API PaLM ?**  
   - a) Augmenter la vitesse des réponses.  
   - b) Fournir une traduction automatique.  
   - c) Bloquer les contenus mettant en danger la sécurité des enfants, entre autres préjudices majeurs.  
   - d) Améliorer la qualité visuelle des sorties.

3. **Quel est le but des tests adverses dans le développement des modèles d'IA générative ?**  
   - a) Réduire le temps d'entraînement des modèles.  
   - b) Identifier les faiblesses en tentant de produire des sorties nuisibles ou dangereuses.  
   - c) Améliorer l'interface utilisateur de l'application.  
   - d) Augmenter la taille du jeu de données pour un meilleur entraînement.