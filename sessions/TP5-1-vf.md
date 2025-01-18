
### TP : Mise en Place d’un Système RAG (Retrieval-Augmented Generation) pour la Documentation Technique

**Objectif**  
Dans ce TP, vous allez construire un pipeline de **Retrieval-Augmented Generation (RAG)** permettant d’interroger des documentations techniques [Exemple](https://python-docs.project.erios.ai/) . Vous utiliserez des sources comme :   
- [PyTorch Documentation sur GitHub](https://github.com/pytorch/pytorch/tree/main/docs)  

Le but est de concevoir un système qui :  
1. Stocke et indexe les documents sous une base de données vectorielle.  
2. Permet de poser des questions et de récupérer des passages pertinents.  
3. Génère des réponses précises avec une IA générative en utilisant les passages récupérés.

---

### Consignes Générales

1. **Sources de Documentation**
   Vous pouvez choisir une ou plusieurs des sources suivantes :  
   - Documentation Python disponible en ligne.  
   - Documentation PyTorch disponible dans le dépôt GitHub. Téléchargez-la en local en clonant le dépôt :  
     ```bash
     git clone https://github.com/pytorch/pytorch.git
     ```  
     Les fichiers de documentation sont situés dans le répertoire `docs/`.

2. **But du TP**  
   Construire un pipeline qui combine :  
   - **Extraction** : Collecte et pré-traitement des fichiers de documentation (par exemple, conversion de `.rst` ou `.md` en texte brut).  
   - **Indexation** : Création d’une base vectorielle pour rechercher des passages pertinents.  
   - **Récupération et génération** : Utilisation des passages pour générer des réponses précises avec une IA.

3. **Libre à vous d'explorer**  
   Vous êtes encouragé à expérimenter avec différents outils, bibliothèques et techniques comme le **re-ranking** ou l’utilisation de différentes bases vectorielles.

---

### Ressources pour Vous Aider

- **Base de données vectorielle** : FAISS, PGVector, Weaviate.  
- **Embedding** : SentenceTransformers, Mistral-embed  
- **Prompt Engineering** : Techniques pour optimiser les interactions avec l’IA générative.  


