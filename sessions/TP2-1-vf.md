# TP : Accéder à une API d'IA Générative Gratuitement avec Mistral AI et Groq

## **Objectif**
Dans ce TP, vous apprendrez à utiliser des APIs d’IA générative gratuites pour vos projets de développement, en utilisant **"La Plateforme" de Mistral AI** et **GroqCloud**.

---

## **1. Présentation des Solutions**

### **Mistral AI**
Mistral AI est une startup française spécialisée dans les modèles de langage de grande envergure (LLM). Sa solution **"La Plateforme"** permet aux développeurs d’accéder à des modèles comme **Mistral-7B** et **Falcon** via une infrastructure serverless, avec une offre gratuite pour les tests et le prototypage.

### **Groq**
Groq est une entreprise américaine qui conçoit des puces d’inférence pour IA. Avec **GroqCloud**, ils offrent un accès API à des modèles d’IA optimisés pour leur matériel, notamment **LLaMA** et des modèles personnalisés comme **GroqGPT**.

---

## **2. Accès API avec Mistral AI**

### **Étape 1 : Inscription sur La Plateforme**
1. Rendez-vous sur [le site officiel de Mistral AI](https://mistral.ai).
2. Cliquez sur **Sign Up** et créez un compte.
3. Une fois inscrit, connectez-vous à **La Plateforme**.
4. Accédez au plan gratuit pour démarrer sans frais.

### **Étape 2 : Récupérer une clé API**
1. Abonnez vous à l'abonnement gratuit.
2. Créez une clé API.
3. Chosissez un modèle.

### **Étape 3 : Intégration de l’API dans votre Application**
Utilisez l’URL et la clé API pour effectuer des requêtes HTTP. Voici un exemple en Python :

```python
from openai import OpenAI  # Import OpenAI module for interacting with the OpenAI API

client = OpenAI(
    base_url="https://api.mistral.ai/v1/",  
    api_key="votre_clé_api",  # Fetch the API key from environment variables
)

# Initial system message to define the assistant's behavior or persona
messages = [
    {"role": "system", "content": ''' YOU ARE AN AGENT ! '''},  # Initial instruction for the AI system
    {"role": "user", "content": '''Give me an idea to be rich '''}, 
]
response = client.chat.completions.create(
    model="your_model",  # Use the model defined in environment variables
    messages=messages,  # Pass the conversation history (including system and user messages)
    stream=False  # Disable streaming, wait for the full response
)

# Retrieve and display the assistant's response
ai_response = response.choices[0].message.content
print(ai_response)
```

---

## **3. Accès API avec Groq**

### **Étape 1 : Inscription sur GroqCloud**
1. Rendez-vous sur [le site officiel de Groq](https://groq.com).
2. Cliquez sur **Sign Up** et créez un compte.
3. Une fois inscrit, connectez-vous à la console **GroqCloud**.
4. Profitez du plan gratuit qui inclut un quota limité d’utilisation (par exemple, 5 000 requêtes gratuites).

### **Étape 2 : Sélection d’un Modèle IA**
1. Accédez à la section **Models** dans GroqCloud.
2. Choisissez un modèle tel que :
   - **LLaMA (Meta)**
   - **GroqGPT**
   - Autres modèles open source supportés.

### **Étape 3 : Récupérer une clé API**
1. Abonnez vous à l'abonnement gratuit.
2. Créez une clé API.
3. Chosissez un modèle.

### **Étape 4 : Intégration de l’API dans votre Application**
Voici un exemple Python pour utiliser GroqCloud :

```python
from openai import OpenAI  # Import OpenAI module for interacting with the OpenAI API

client = OpenAI(
    base_url="https://api.groq.com/openai/v1",  # Fetch the API endpoint from environment variables
    api_key="votre_clé_api",  # Fetch the API key from environment variables
)

# Initial system message to define the assistant's behavior or persona
messages = [
    {"role": "system", "content": ''' YOU ARE AN AGENT ! '''},  # Initial instruction for the AI system
    {"role": "user", "content": '''Give me an idea to be rich '''}, 
]
response = client.chat.completions.create(
    model="your_model",  # Use the model defined in environment variables
    messages=messages,  # Pass the conversation history (including system and user messages)
    stream=False  # Disable streaming, wait for the full response
)

# Retrieve and display the assistant's response
ai_response = response.choices[0].message.content
print(ai_response)
```

---

## **4. Comparaison des Solutions**

| **Critères**        | **Mistral AI**                     | **Groq**                           |
|---------------------|------------------------------------|------------------------------------|
| Modèles disponibles | Uniquement des modèles Mistral          | LLaMA, Mistral, Gemma |
| Plateforme          | La Plateforme (serverless)        | GroqCloud (IA hardware-based)     |
| Coût                | Plan gratuit disponible élevé           | Quota gratuit limité              |
| Public cible        | Développeurs d’applications IA    | Développeurs et chercheurs IA     |

---

## **Conclusion**
En utilisant **"La Plateforme" de Mistral** et **GroqCloud**, vous avez accès à des outils puissants pour créer et expérimenter avec des applications IA génératives. Profitez des offres gratuites pour démarrer et découvrir les avantages respectifs de chaque solution.

