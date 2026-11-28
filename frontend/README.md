# Front-end : application React (PWA)

Structure prévue (voir `docs/03-architecture.md`) :

```
frontend/
├── public/
└── src/
    ├── api/            # client Axios, appels par domaine
    ├── components/     # ui/ (boutons, champs, cartes), layout/
    ├── features/       # auth, catalog, cart, orders, reviews, seller, admin
    ├── hooks/
    ├── lib/            # validation, formatage, utilitaires
    ├── pages/
    ├── routes/         # routes et gardes par rôle
    ├── styles/
    └── tests/
```

## Démarrage (après l'initialisation du Sprint 0, tâche S0-11)

```bash
npm install
npm run dev        # http://localhost:5173
npm test
```

La variable `VITE_API_URL` (voir `../.env.example`) pointe vers l'API.

Les dépendances de `package.json` sont un point de départ : les versions sont à confirmer lors de l'initialisation (ajouter ESLint et Prettier à ce moment).
