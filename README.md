<div align="center">

# 🧭 JobMatch AI

### Votre agent d'orientation professionnelle propulsé par l'intelligence artificielle

En **13 questions**, JobMatch AI analyse votre profil, vos émotions et vos ambitions
pour vous proposer un tableau de bord d'orientation personnalisé — **adapté à votre pays**.

[![Démo en ligne](https://img.shields.io/badge/🌐_Démo_en_ligne-Essayer-3FAF7A?style=for-the-badge)](https://jobmatch-ai-qt8b.vercel.app)
&nbsp;
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Claude AI](https://img.shields.io/badge/Claude_AI-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

</div>

---

## ✨ Aperçu

> 🔗 **Démo en direct : [jobmatch-ai-qt8b.vercel.app](https://jobmatch-ai-qt8b.vercel.app)**

<!-- 📸 Ajoute une capture d'écran ici pour un maximum d'impact !
     Mets une image dans un dossier "docs/" puis décommente la ligne ci-dessous : -->
<!-- ![Aperçu du tableau de bord](docs/screenshot.png) -->

JobMatch AI est une application web qui aide les étudiants et les personnes en reconversion
à **découvrir des métiers qui leur correspondent vraiment**. Contrairement aux tests
d'orientation classiques, elle prend en compte non seulement les intérêts, mais aussi
les **émotions**, les **peurs** et les **ambitions profondes** de l'utilisateur — puis
adapte ses recommandations aux **filières réellement disponibles dans son pays**.

## 🎯 Fonctionnalités

- **🧠 Quiz intelligent en 13 questions** — intérêts, émotions dominantes, peurs professionnelles, rêve de carrière.
- **🌍 Recommandations localisées** — le Top 3 des métiers est filtré selon les filières disponibles dans le pays choisi.
- **📊 Tableau de bord personnalisé** — 2 types de personnalité, scores de compatibilité, radar de compétences (6 dimensions).
- **🎓 Recherche d'universités en temps réel** — les établissements du pays de l'utilisateur sont trouvés via recherche web.
- **💬 Justifications sur-mesure** — chaque métier recommandé est expliqué en lien avec les réponses et les émotions exprimées.

## 🤖 Comment ça marche ?

L'application est une **Single Page Application** légère (HTML/CSS/JS, sans framework)
qui dialogue avec l'API de Claude via une **fonction serverless** faisant office de proxy
sécurisé — la clé API n'est **jamais** exposée côté client.

```
┌──────────────┐      POST       ┌──────────────────┐     API      ┌───────────────┐
│  Navigateur  │  ───────────▶   │  /api/chat.js    │  ─────────▶  │   Claude API  │
│ (index.html) │                 │ (proxy serverless│              │ (Anthropic)   │
│              │  ◀───────────   │  cache la clé)   │  ◀─────────  │               │
└──────────────┘   JSON réponse  └──────────────────┘              └───────────────┘
```

Deux appels à Claude alimentent l'expérience :
1. **Génération du bilan** — analyse des réponses → profil, Top 3 métiers, dimensions, conseils (JSON structuré).
2. **Recherche d'universités** — recherche web pour trouver des établissements réels par métier et par pays.

## 🛠️ Stack technique

| Côté | Technologies |
|------|--------------|
| **Front-end** | HTML5, CSS3 (design system maison), JavaScript vanilla |
| **Back-end** | Fonction serverless Node.js (proxy API) |
| **IA** | API Claude (Anthropic) — modèle `claude-haiku-4-5` |
| **Hébergement** | Vercel |

## 📁 Structure du projet

```
jobmatch-ai/
├── api/
│   └── chat.js          ← Proxy serverless (protège la clé API)
├── public/
│   └── index.html       ← L'application complète (SPA)
├── vercel.json          ← Configuration Vercel
├── package.json         ← Configuration Node.js
└── README.md
```

## 🚀 Installation & déploiement

### Prérequis
- Un compte [Vercel](https://vercel.com)
- Une clé API [Anthropic](https://console.anthropic.com/keys)

### Déployer
1. **Fork / clone** ce dépôt.
2. Importe le projet sur **Vercel** (*Add New Project*).
3. Ajoute la variable d'environnement :
   - `ANTHROPIC_API_KEY` = ta clé `sk-ant-...`
4. **Déploie** — Vercel construit et met en ligne automatiquement.

> 🔒 La clé API reste côté serveur, dans les variables d'environnement Vercel. Elle n'apparaît jamais dans le code client.

## 🗺️ Améliorations envisagées

- [ ] Sauvegarde du profil pour retrouver ses résultats
- [ ] Export du tableau de bord en PDF
- [ ] Historique des métiers explorés
- [ ] Version multilingue

## 👤 Réalisé par

**Aya Aidibi** — projet personnel d'orientation par l'IA.


