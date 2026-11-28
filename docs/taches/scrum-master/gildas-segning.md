# 🧭 SEGNING WOUATI Gildas

**Scrum Master** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Faciliter le Scrum, garder le backlog à jour, installer le cadre collaboratif (Git, intégration continue, environnements), documenter et déployer.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Scrum Master |
| **Domaine** | Gestion de projet |
| **Dossiers de travail** | `.github/`, `docs/`, `README.md`, `Environnements Cloudflare Pages, Render et Neon` |
| **Votre branche** | `gildas` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 5 | 2 |
| Sprint 1 | 1 | 0 |
| Sprint 2 | 1 | 0 |
| Sprint 3 | 2 | 0 |
| Phase pilote | 3 | 2 |
| Tâches transversales (tous les sprints) | 2 | 2 |
| **Total** | **14** | **6** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-01** : Rédiger la vision, les user stories et le backlog initial
  - Côté : Gestion de projet · Dossier : `docs/`
  - Livrable : Product backlog priorisé
  - Appui : Souop
- [ ] **S0-04** : Définir la Definition of Done et les conventions Git
  - Côté : Gestion de projet · Dossier : `docs/ et .github/`
  - Livrable : Document de conventions
  - Appui : Nzemkam
- [ ] **S0-05** : Créer le dépôt GitHub, les branches, l'intégration continue
  - Côté : Gestion de projet · Dossier : `.github/workflows/`
  - Livrable : Dépôt configuré
  - Appui : Nzemkam
- [ ] **S0-06** : Identifier les risques et préparer un plan de mitigation
  - Côté : Gestion de projet · Dossier : `docs/`
  - Livrable : Registre des risques
  - Appui : Nzemkam
- [ ] **S0-14** : Rédiger le README
  - Côté : Gestion de projet · Dossier : `README.md`
  - Livrable : README.md
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S0-02** : Finaliser l'étude de marché, le persona et l'analyse de la concurrence
  - Responsable : Souop · Côté : Client · Livrable : Dossier d'étude de marché
- [ ] **S0-03** : Recueillir et valider les besoins des utilisateurs
  - Responsable : Souop · Côté : Client · Livrable : Liste de besoins validée

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-14** : Déployer un environnement de test
  - Côté : Gestion de projet · Dossier : `Cloudflare Pages, Render, Neon, .github/workflows/`
  - Livrable : URL de test
  - Appui : Nzemkam

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-17** : Mise à jour de la documentation et de l'environnement de test
  - Côté : Gestion de projet · Dossier : `docs/ et README.md`
  - Livrable : Documentation à jour
  - Appui : —

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-18** : Guide d'utilisation en français (texte et captures)
  - Côté : Gestion de projet · Dossier : `docs/guide-utilisateur.md`
  - Livrable : Guide utilisateur
  - Appui : Angue
- [ ] **S3-19** : Déploiement en production, sauvegardes de la base, documentation finale
  - Côté : Gestion de projet · Dossier : `Render, Cloudflare Pages, Neon, docs/deploiement.md`
  - Livrable : Application en ligne
  - Appui : Nzemkam

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### ✅ Vous êtes responsable

- [ ] **P-02** : Former les utilisateurs et les accompagner
  - Côté : Client · Dossier : `docs/pilote/`
  - Livrable : Sessions de formation
  - Appui : Angue
- [ ] **P-06** : Préparer la présentation et la démonstration finale
  - Côté : Gestion de projet · Dossier : `docs/pilote/`
  - Livrable : Soutenance
  - Appui : Toute l'équipe
- [ ] **P-07** : Rétrospective finale et bilan du projet
  - Côté : Gestion de projet · Dossier : `docs/pilote/`
  - Livrable : Bilan de projet
  - Appui : Toute l'équipe

#### 🤝 Vous êtes en appui

- [ ] **P-01** : Organiser le pilote et recruter les producteurs testeurs
  - Responsable : Souop · Côté : Client · Livrable : Liste des participants
- [ ] **P-03** : Assurer le support pendant le pilote (téléphone, WhatsApp)
  - Responsable : Souop · Côté : Client · Livrable : Journal des demandes

### Tâches transversales (tous les sprints)

_Objectif : faire vivre la méthode Scrum et la qualité tout au long du projet._

#### ✅ Vous êtes responsable

- [ ] **T-01** : Mettre à jour le backlog et le tableau Kanban
  - Côté : Gestion de projet · Dossier : `Tableau Kanban (GitHub Projects)`
  - Livrable : Après chaque réunion
  - Appui : Souop
- [ ] **T-02** : Rédiger le compte rendu de sprint et suivre l'avancement (burndown)
  - Côté : Gestion de projet · Dossier : `docs/`
  - Livrable : Fin de sprint
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **T-04** : Présenter les fonctionnalités terminées
  - Responsable : Chaque développeur · Côté : Gestion de projet · Livrable : Sprint Review
- [ ] **T-06** : Valider les priorités métier
  - Responsable : Souop · Côté : Client · Livrable : Sprint Planning

---

## 🔁 Cérémonies à animer (à chaque sprint)

### Sprint 1

- [ ] Sprint Planning (1 à 2 h) : objectif du sprint, tâches, charge de chacun
- [ ] Daily Scrum (15 min, chaque jour de travail)
- [ ] Sprint Review (1 h) : démonstration au Product Owner et au client
- [ ] Rétrospective (45 min) : ce qui marche, ce qui bloque, actions d'amélioration

### Sprint 2

- [ ] Sprint Planning (1 à 2 h) : objectif du sprint, tâches, charge de chacun
- [ ] Daily Scrum (15 min, chaque jour de travail)
- [ ] Sprint Review (1 h) : démonstration au Product Owner et au client
- [ ] Rétrospective (45 min) : ce qui marche, ce qui bloque, actions d'amélioration

### Sprint 3

- [ ] Sprint Planning (1 à 2 h) : objectif du sprint, tâches, charge de chacun
- [ ] Daily Scrum (15 min, chaque jour de travail)
- [ ] Sprint Review (1 h) : démonstration au Product Owner et au client
- [ ] Rétrospective (45 min) : ce qui marche, ce qui bloque, actions d'amélioration

---

## 🧰 Boîte à outils et règles

- **Outils** : GitHub (dépôt, Projects, Actions), Cloudflare Pages, Render, Neon, tableau Kanban.
- **Méthode** : cérémonies à chaque sprint, backlog à jour après chaque réunion, blocages levés dans la journée, documentation tenue à jour.
- **Références** : `CONTRIBUTING.md`, `docs/05-repartition-des-taches.md`.

## ✅ Definition of Done

Une tâche est terminée lorsque :

- [ ] le code est relu par au moins un autre membre (Pull Request approuvée) ;
- [ ] les tests automatisés passent ;
- [ ] la fonctionnalité a été testée par la QA ;
- [ ] elle est déployée sur l'environnement de test ;
- [ ] elle a été validée par le représentant client ;
- [ ] la documentation concernée est à jour.

## 🔗 Liens utiles

- [Cahier des charges](../../01-cahier-des-charges.md)
- [Stack technologique](../../02-stack-technologique.md)
- [Architecture](../../03-architecture.md)
- [Requirements](../../04-requirements.md)
- [Répartition globale](../../05-repartition-des-taches.md)
