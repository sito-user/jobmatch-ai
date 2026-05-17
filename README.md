# JobMatch AI — Déploiement Vercel

## Structure du projet
```
jobmatch-ai/
├── api/
│   └── chat.js          ← Serveur proxy (cache la clé API)
├── public/
│   └── index.html       ← L'application JobMatch AI
├── vercel.json          ← Configuration Vercel
├── package.json         ← Config Node.js
└── README.md
```

## Déploiement sur Vercel

### Étape 1 — Pusher sur GitHub
```bash
git init
git add .
git commit -m "JobMatch AI initial"
git branch -M main
git remote add origin https://github.com/VOTRE_USERNAME/jobmatch-ai.git
git push -u origin main
```

### Étape 2 — Connecter Vercel
1. Allez sur vercel.com
2. Cliquez "Add New Project"
3. Importez votre repo GitHub "jobmatch-ai"
4. Cliquez "Deploy"

### Étape 3 — Ajouter la clé API (IMPORTANT)
1. Sur Vercel, allez dans votre projet
2. Settings → Environment Variables
3. Ajoutez : 
   - Name: ANTHROPIC_API_KEY
   - Value: votre clé sk-ant-...
4. Cliquez Save
5. Redéployez (Deployments → Redeploy)

Votre site sera accessible sur : https://jobmatch-ai.vercel.app
