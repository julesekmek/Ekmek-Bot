# ⚡ Quick Start - Ekmek-Bot

## 🚀 Test Local (2 minutes)

### 1. Démarrer le serveur
```bash
npm start
```

### 2. Tester l'interface
Ouvrir http://localhost:3000 dans votre navigateur

### 3. Tester l'API
```bash
curl -X POST http://localhost:3000/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Qu'\''est-ce que l'\''IA Product Management ?"}'
```

## 🌐 Déploiement Rapide

### Option 1: Render (Recommandé)
1. Pousser sur GitHub
2. Aller sur [Render.com](https://render.com)
3. **New Web Service** → Connecter repo
4. Build: `npm install`
5. Start: `npm start`
6. Variables: `OPENAI_API_KEY=sk-... (à renseigner dans votre .env, ne jamais publier)`

### Option 2: Vercel
```bash
npm i -g vercel
vercel --prod
```

## 🔗 Code iframe pour LinkedIn

### Desktop/Tablet (Recommandé)
```html
<iframe 
    src="https://your-deployed-url.com" 
    width="600" 
    height="500" 
    frameborder="0"
    style="border-radius: 20px; box-shadow: 0 8px 32px rgba(0,0,0,0.3);">
</iframe>
```

### Mobile (Responsive)
```html
<iframe 
    src="https://your-deployed-url.com" 
    width="100%" 
    height="450" 
    frameborder="0"
    style="max-width: 600px; border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.2);">
</iframe>
```

## ✅ Checklist de Test

- [ ] Serveur démarre sans erreur
- [ ] Interface s'affiche correctement
- [ ] Chat fonctionne (question/réponse)
- [ ] Questions sur le créateur → lien LinkedIn
- [ ] Health check `/health` répond OK
- [ ] Design responsive (test sur mobile/tablet)
- [ ] Déploiement réussi
- [ ] iframe fonctionne sur le site cible

## 📱 Test Responsive

Testez le chatbot sur différents appareils :
- **Desktop** : 600×500px
- **Tablet** : 600×500px (responsive)
- **Mobile** : 100%×450px
- **Small Mobile** : 100%×400px

## 🆘 Problèmes Courants

**Serveur ne démarre pas**
- Vérifier Node.js >= 16
- Vérifier le fichier `.env`
- Vérifier `npm install`

**Erreur OpenAI**
- Vérifier la clé API
- Vérifier les crédits OpenAI

**Interface ne s'affiche pas**
- Vérifier le port 3000
- Vérifier les logs du serveur

**Problèmes responsive**
- Vérifier la meta viewport tag
- Tester sur différents appareils
- Vérifier les media queries

## 📞 Support

- **Documentation complète** : README.md
- **Guide déploiement** : DEPLOYMENT.md
- **Créateur** : Jules EKMEKDJIAN sur LinkedIn 