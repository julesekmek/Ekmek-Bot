# 🤖 Ekmek-Bot - IA Product Management Assistant

Un chatbot IA spécialisé dans la transition d'un Product Manager au rôle de IA Product Manager, créé par Jules EKMEKDJIAN.

## 🎯 Objectif

Ekmek-Bot est un assistant conversationnel gratuit et embarquable (iframe) qui répond aux questions sur :
- IA Product Management
- Product Management classique
- UX/UI Design
- Gestion de projet

## 🛠️ Stack Technique

| Composant | Technologie |
|-----------|-------------|
| Frontend UI | HTML + JavaScript (Vanilla) |
| Backend Proxy | Node.js + Express |
| AI Engine | OpenAI GPT-3.5-turbo |
| Data Source | JSON Q&A curated |
| Styling | CSS avec gradients personnalisés |

## 🚀 Installation & Démarrage

### Prérequis
- Node.js >= 16.0.0
- npm ou yarn
- Clé API OpenAI

### 1. Cloner le projet
```bash
git clone <repository-url>
cd ekmek-bot
```

### 2. Installer les dépendances
```bash
npm install
```

### 3. Configuration environnement
Créer un fichier `.env` à la racine du projet :
```env
OPENAI_API_KEY=sk-... (à renseigner dans votre .env, ne jamais publier)
PORT=3000
```

### 4. Lancer le serveur
```bash
# Production
npm start

# Développement (avec auto-reload)
npm run dev
```

Le chatbot sera accessible sur `http://localhost:3000`

## 📁 Structure du Projet

```
project-root/
│
├── public/
│   ├── index.html         ← Interface chatbot
│   └── qa.json           ← Données Q&A d'entraînement
│
├── server.js             ← Serveur Express
├── package.json          ← Dépendances
├── .env                  ← Variables d'environnement
└── README.md            ← Documentation
```

## 🎨 Personnalisation

### Modifier les Q&A
Éditez le fichier `public/qa.json` pour ajouter/modifier les questions et réponses.

### Personnaliser le style
Modifiez les styles CSS dans `public/index.html` :
- Couleurs : gradients `#FFE99A` vers `#FF5F5F`
- Taille : max-width 400px pour l'iframe
- Animations : fadeIn et bounce

## 🌐 Déploiement

### Render
1. Connecter le repository GitHub
2. Configurer les variables d'environnement
3. Build command : `npm install`
4. Start command : `npm start`

### Vercel
1. Installer Vercel CLI : `npm i -g vercel`
2. Déployer : `vercel --prod`

### Railway
1. Connecter le repository
2. Ajouter les variables d'environnement
3. Déploiement automatique

## 🔗 Intégration iframe

```html
<iframe 
    src="https://your-deployed-url.com" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 10px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
</iframe>
```

## 🧠 Comportement du Bot

### Règles de comportement
1. **Spécialisation** : Répond uniquement aux questions sur IA PM, PM, UX/UI, gestion de projet
2. **Sécurité** : Refuse les questions personnelles/sensibles
3. **Créateur** : Mentionne Jules EKMEKDJIAN et redirige vers LinkedIn
4. **Éthique** : Pas de conseils médicaux/juridiques/financiers
5. **Qualité** : Réponses claires et concises en français

### Gestion des cas spéciaux
- **Questions sur le créateur** : Réponse automatique avec lien LinkedIn
- **Contenu offensant** : Arrêt de la conversation
- **Compétences de Jules** : Réponse humoristique

## 📊 API Endpoints

### POST /chat
Envoie un message au chatbot
```json
{
  "message": "Qu'est-ce que l'IA Product Management ?"
}
```

Réponse :
```json
{
  "response": "L'IA Product Management consiste à..."
}
```

### GET /health
Vérification de l'état du service
```json
{
  "status": "OK",
  "timestamp": "2024-01-01T12:00:00.000Z",
  "qaCount": 30
}
```

## 🔧 Maintenance

### Ajouter de nouvelles Q&A
1. Éditer `public/qa.json`
2. Redémarrer le serveur
3. Tester avec des questions similaires

### Monitoring
- Logs de démarrage avec nombre de Q&A chargées
- Gestion d'erreurs OpenAI API
- Health check endpoint

## 🛡️ Sécurité

- Validation des inputs utilisateur
- Filtrage du contenu offensant
- Gestion sécurisée de l'API key OpenAI
- Rate limiting recommandé en production

## 📈 Évolutions Futures

- [ ] Support de conversations multi-tours
- [ ] Analytics des questions fréquentes
- [ ] Interface d'administration pour Q&A
- [ ] Support multi-langues
- [ ] Intégration avec CRM

## 👨‍💻 Créateur

**Jules EKMEKDJIAN** - IA Product Manager
- LinkedIn : https://www.linkedin.com/in/jules-ekmekdjian/
- Spécialisé en transition PM → PM IA

---

*Ekmek-Bot - Votre assistant IA Product Management* 🤖 