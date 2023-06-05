# Atelier : Créer une application simple de liste de tâches avec Node.js et MongoDB

Dans cet atelier, nous allons construire une application simple de liste de tâches avec Node.js et MongoDB. Nous allons utiliser `axios` pour récupérer les données et `mongoose` pour interagir avec notre base de données MongoDB.

Tout au long de cet atelier, nous allons compléter des fragments de code dans un projet fourni.

## Partie 0 : Préparation de l'environnement

- Installez Node.js et npm : https://nodejs.org/en/download/
- Installez MongoDB : https://www.mongodb.com/try/download/community
- Installez les dépendances du projet : `npm install`

## Partie 1 : Configuration de la connexion à MongoDB

1.1 Dans votre fichier `server.js`, importez `mongoose` :

```javascript
const mongoose = require('mongoose');
```

1.2 Ajoutez le code suivant pour connecter votre application Node.js à votre instance MongoDB :

```javascript
const uri = "mongodb://localhost:27017/todoApp"; // Remplacez par l'URI de votre base de données si nécessaire

mongoose.connect(uri, { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log("MongoDB connected..."))
  .catch(err => console.log(err));
```

## Partie 2 : Création du modèle de données

2.1 Créez un nouveau fichier `models/Todo.js` et ajoutez le code suivant pour définir un modèle de données pour une tâche :

```javascript
const mongoose = require('mongoose');

const TodoSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
  },
  completed: {
    type: Boolean,
    default: false,
  },
});

module.exports = mongoose.model('Todo', TodoSchema);
```

## Partie 3 : Création de routes pour gérer les tâches

3.1 Dans votre fichier `server.js`, importez le modèle `Todo` et définissez les routes pour gérer les tâches :

```javascript
const Todo = require('./models/Todo');

// TODO: définir les routes ici
```

3.2 Ajoutez la route pour obtenir toutes les tâches :

```javascript
app.get('/todos', async (req, res) => {
  // TODO: Récupérer toutes les tâches de la base de données
});
```

3.3 Ajoutez la route pour créer une nouvelle tâche :

```javascript
app.post('/todos', async (req, res) => {
  // TODO: Créer une nouvelle tâche dans la base de données
});
```

3.4 Ajoutez la route pour mettre à jour une tâche :

```javascript
app.put('/todos/:id', async (req, res) => {
  // TODO: Mettre à jour une tâche dans la base de données
});
```

3.5 Ajoutez la route pour supprimer une tâche :

```javascript
app.delete('/todos/:id', async (req, res) => {
  // TODO: Supprimer une tâche de la base de données
});
```

## Partie 4 : Interagir avec le serveur depuis l'application cliente

4.1 Installez `axios` dans votre application cliente avec `npm install axios`.

4.2 Importez `axios` dans votre composant qui gère les tâches :

```javascript
import axios from

 'axios';
```

4.3 Utilisez `axios` pour obtenir toutes les tâches du serveur quand le composant est monté :

```javascript
useEffect(() => {
  // TODO: obtenir toutes les tâches du serveur
}, []);
```

4.4 Utilisez `axios` pour créer une nouvelle tâche quand l'utilisateur remplit le formulaire :

```javascript
const createTodo = async (title) => {
  // TODO: créer une nouvelle tâche sur le serveur
};
```

4.5 Utilisez `axios` pour mettre à jour une tâche quand l'utilisateur coche/décoche la case :

```javascript
const updateTodo = async (id, completed) => {
  // TODO: mettre à jour la tâche sur le serveur
};
```

4.6 Utilisez `axios` pour supprimer une tâche quand l'utilisateur clique sur le bouton de suppression :

```javascript
const deleteTodo = async (id) => {
  // TODO: supprimer la tâche du serveur
};
```

Bravo ! Vous avez maintenant une application de liste de tâches fonctionnelle qui utilise Node.js et MongoDB. Vous pouvez explorer davantage et ajouter d'autres fonctionnalités à votre application. Bon codage !
