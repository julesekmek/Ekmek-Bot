# 🚀 Guide de Déploiement - Ekmek-Bot

## Plateformes Recommandées

### 1. Render (Recommandé - Gratuit)

#### Étape 1: Préparation
1. Pousser le code sur GitHub
2. Créer un compte sur [Render.com](https://render.com)

#### Étape 2: Configuration
1. **New Web Service** → Connecter le repository GitHub
2. **Build Command**: `npm install`
3. **Start Command**: `npm start`
4. **Environment Variables**:
   ```
   OPENAI_API_KEY=sk-... (à renseigner dans votre .env, ne jamais publier)
   PORT=10000
   ```

#### Étape 3: Déploiement
- Render déploie automatiquement
- URL générée : `https://ekmek-bot.onrender.com`

### 2. Vercel (Alternative - Gratuit)

#### Étape 1: Installation CLI
```bash
npm i -g vercel
```

#### Étape 2: Configuration
1. `vercel login`
2. `vercel` (suivre les prompts)
3. Ajouter les variables d'environnement dans le dashboard Vercel

#### Étape 3: Déploiement
```bash
vercel --prod
```

### 3. Railway (Alternative - Payant après usage gratuit)

#### Étape 1: Connexion
1. Aller sur [Railway.app](https://railway.app)
2. Connecter le repository GitHub

#### Étape 2: Configuration
1. **New Project** → Deploy from GitHub repo
2. Ajouter les variables d'environnement dans l'onglet Variables

#### Étape 3: Déploiement
- Déploiement automatique à chaque push

## 🔧 Configuration Post-Déploiement

### 1. Test du Health Check
```bash
curl https://your-app-url.com/health
```
Réponse attendue :
```json
{
  "status": "OK",
  "timestamp": "2024-01-01T12:00:00.000Z",
  "qaCount": 30
}
```

### 2. Test du Chatbot
```bash
curl -X POST https://your-app-url.com/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Qu\'est-ce que l\'IA Product Management ?"}'
```

### 3. Test de l'Interface
Ouvrir `https://your-app-url.com` dans un navigateur

## 🔗 Intégration iframe

### Code HTML pour LinkedIn (Nouvelles dimensions)
```html
<iframe 
    src="https://your-app-url.com" 
    width="600" 
    height="500" 
    frameborder="0"
    style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0,0,0,0.3); border: 1px solid rgba(255,255,255,0.1);">
</iframe>
```

### Code HTML pour site web (Responsive)
```html
<div style="text-align: center; margin: 20px 0;">
    <iframe 
        src="https://your-app-url.com" 
        width="100%" 
        height="500" 
        style="max-width: 600px; border-radius: 20px; box-shadow: 0 8px 32px rgba(0,0,0,0.3); border: 1px solid rgba(255,233,154,0.2);">
    </iframe>
</div>
```

### Code HTML pour mobile (Optimisé)
```html
<iframe 
    src="https://your-app-url.com" 
    width="100%" 
    height="450" 
    frameborder="0"
    style="border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.2);">
</iframe>
```

## 📱 Responsive Design

Le chatbot s'adapte automatiquement aux différentes tailles d'écran :

- **Desktop (>1200px)** : 700px × 550px
- **Tablet (768px-1200px)** : 600px × 500px  
- **Mobile (480px-768px)** : 100% × 450px
- **Small Mobile (<480px)** : 100% × 400px
- **Landscape Mobile** : Hauteur réduite à 350px

## 📊 Monitoring

### Métriques à surveiller
- **Uptime** : Disponibilité du service
- **Response Time** : Temps de réponse des requêtes
- **Error Rate** : Taux d'erreurs
- **API Usage** : Utilisation de l'API OpenAI

### Logs importants
- Démarrage du serveur
- Nombre de Q&A chargées
- Erreurs OpenAI API
- Requêtes malformées

## 🛡️ Sécurité en Production

### Variables d'environnement
- ✅ Toujours utiliser des variables d'environnement
- ❌ Ne jamais commiter les clés API
- 🔄 Rotation régulière des clés

### Rate Limiting (Recommandé)
```javascript
// Ajouter dans server.js
const rateLimit = require('express-rate-limit');

const limiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100 // limite chaque IP à 100 requêtes par fenêtre
});

app.use('/chat', limiter);
```

### CORS (Si nécessaire)
```javascript
// Ajouter dans server.js
const cors = require('cors');
app.use(cors({
  origin: ['https://linkedin.com', 'https://your-domain.com']
}));
```

## 🔄 Mise à Jour

### Processus de mise à jour
1. Modifier le code localement
2. Tester en local : `npm start`
3. Pousser sur GitHub
4. Déploiement automatique sur la plateforme

### Rollback
- Render : Dashboard → Deployments → Rollback
- Vercel : Dashboard → Deployments → Revert
- Railway : Dashboard → Deployments → Rollback

## 💰 Coûts Estimés

### Render
- **Gratuit** : 750h/mois
- **Payant** : $7/mois pour usage illimité

### Vercel
- **Gratuit** : 100GB bandwidth/mois
- **Payant** : $20/mois pour usage illimité

### OpenAI API
- **GPT-3.5-turbo** : ~$0.002/1K tokens
- **Estimation** : $5-20/mois selon usage

## 🆘 Dépannage

### Problèmes courants

#### 1. Serveur ne démarre pas
```bash
# Vérifier les logs
npm start

# Vérifier les variables d'environnement
echo $OPENAI_API_KEY
```

#### 2. Erreur OpenAI API
- Vérifier la validité de la clé API
- Vérifier les crédits OpenAI
- Vérifier les limites de rate

#### 3. Q&A non chargées
- Vérifier le fichier `public/qa.json`
- Vérifier les logs de démarrage
- Tester l'endpoint `/health`

#### 4. Interface ne s'affiche pas
- Vérifier l'URL de déploiement
- Vérifier les logs du serveur
- Tester en local d'abord

#### 5. Problèmes de responsive
- Vérifier la meta viewport tag
- Tester sur différents appareils
- Vérifier les media queries CSS

### Support
- **Documentation** : README.md
- **Issues** : GitHub Issues
- **Contact** : Jules EKMEKDJIAN sur LinkedIn 