# Session 2 : Travailler avec les grands modèles de langage
## Partie 1 : L'art du prompt engineering

Le **prompt engineering** est l'art de poser la bonne question pour obtenir les meilleurs résultats d'un LLM. Il permet une interaction directe avec le modèle via des instructions en langage naturel.

Autrefois, travailler avec des modèles d'apprentissage automatique nécessitait une connaissance approfondie des jeux de données, des statistiques et des techniques de modélisation. Aujourd'hui, les LLM peuvent être "programmés" en anglais ou dans d'autres langues.

Devenir un excellent concepteur de prompts ne demande pas d'expérience en programmation. Cependant, la créativité et la persévérance seront vos meilleurs atouts. Voici quelques techniques utiles pour concevoir des prompts efficaces.

---

### Bonnes pratiques pour concevoir des prompts
- **Communiquez clairement** le contenu ou les informations les plus importantes.
- **Structurez votre prompt** : commencez par définir le rôle du modèle, fournissez du contexte/données d'entrée, puis donnez des instructions.
- **Utilisez des exemples spécifiques et variés** pour guider le modèle vers des résultats plus précis.
- **Ajoutez des contraintes** pour limiter la portée des réponses du modèle, évitant ainsi les digressions ou les erreurs factuelles.
- **Décomposez les tâches complexes** en une séquence de tâches plus simples.
- **Demandez au modèle d'évaluer ou de vérifier ses réponses** avant de les fournir (par exemple, "Limitez votre réponse à 3 phrases", "Évaluez votre réponse sur une échelle de 1 à 10", "Pensez-vous que c'est correct ?").

Le plus important : **soyez créatif !** Plus vous êtes ouvert d'esprit, meilleurs seront vos résultats. Le domaine du prompt engineering est encore en pleine évolution.

---

### Types de prompts

#### 1. **Prompt direct (Zero-shot)**
Le **prompt direct**, ou **zero-shot**, est le type de prompt le plus simple. Il ne fournit aucun exemple au modèle, juste une instruction. L'instruction peut être formulée comme une question ou inclure un rôle assigné au modèle.

**Exemples :**

**Génération d'idées :**
```
Prompt : Pouvez-vous me donner une liste d'idées pour des articles de blog destinés aux touristes visitant Paris pour la première fois ?
```

**Prompt avec rôle :**
```
Prompt : Vous êtes un puissant robot générateur de prompts. Votre mission est de comprendre mes objectifs, poser des questions jusqu'à bien cerner mes besoins, puis créer le meilleur prompt possible. Posez-moi une première question sur mon objectif.
```

**Organisation des données :**
```
Prompt : Créez un tableau de 4 colonnes avec 10 films de science-fiction très bien notés, leur année de sortie, la note moyenne des spectateurs, et les 3 mots-clés les plus mentionnés dans les critiques.
Citez la source des notes des spectateurs.
```

---

#### 2. **Prompt avec exemples (One-, few- et multi-shot)**

Le **one-shot prompting** montre un exemple clair et descriptif au modèle pour qu'il l'imite.

**Exemple de génération d'idées :**
```
Prompt :
Donnez des idées d'articles de blog pour des touristes visitant Paris pour la première fois.

1. La Tour Eiffel et au-delà : les endroits à ne pas manquer lors de votre première visite à Paris.
```

Le **few-shot prompting** fournit plusieurs exemples pour des tâches complexes ou lorsque des réponses structurées sont attendues.

**Exemple de classification de sentiments :**
```
Prompt :
Produit génial, 10/10 : Positif  
Ne fonctionne pas bien : Négatif  
Très utile, ça vaut le coup : Positif  
Ça ne marche pas ! :
```

---

#### 3. **Prompt avec chaîne de raisonnement (Chain-of-Thought)**

Le **Chain-of-Thought (CoT)** encourage le modèle à expliquer son raisonnement avant de répondre.

**Exemple :**
```
Prompt :
Les nombres impairs dans ce groupe s'additionnent pour donner un nombre pair : 4, 8, 9, 15, 12, 2, 1.
A : En additionnant les nombres impairs (9, 15, 1), on obtient 25. La réponse est : Faux.
Les nombres impairs dans ce groupe s'additionnent pour donner un nombre pair : 15, 32, 5, 13, 82, 7, 1.
A :
```

---

#### 4. **Zero-shot CoT**
Ajoutez à un prompt zero-shot une instruction telle que : "Réfléchissons étape par étape." Cela incite le modèle à générer une chaîne de raisonnement pour obtenir une réponse plus précise.

**Exemple :**
```
Prompt :
Je suis allé au marché et j'ai acheté 10 pommes. J'ai donné 2 pommes à mon voisin et 2 à un réparateur. J'ai ensuite acheté 5 pommes de plus et mangé 1. Combien de pommes me reste-t-il ?  

Réfléchissons étape par étape.
```

---

### Stratégies pour itérer sur les prompts
Le perfectionnement des prompts peut nécessiter plusieurs (voire des dizaines) d'itérations. Voici quelques conseils pour affiner vos prompts si vous êtes bloqué :

- **Répétez les mots-clés ou idées importantes.**
- **Précisez le format souhaité** pour la sortie (par exemple, CSV, JSON, etc.).
- **Utilisez des majuscules pour insister sur certains points** ou des formulations exagérées pour clarifier vos attentes.
- **Essayez des synonymes ou reformulations.** Documentez ce qui fonctionne ou non.
- **Technique sandwich :** Répétez la même instruction au début et à la fin d'un prompt.

Avec de la pratique et de la persévérance, vous deviendrez un expert du prompt engineering et obtiendrez des résultats optimaux avec les LLMs !