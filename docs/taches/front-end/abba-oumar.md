# 🎨 ABBA Oumar

**Développeur front-end** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Réaliser les parcours d'authentification, de catalogue, de panier et d'administration, branchés sur l'API.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Développeur front-end |
| **Domaine** | Front-end |
| **Dossiers de travail** | `frontend/src/features/auth/`, `frontend/src/features/catalog/`, `frontend/src/features/cart/`, `frontend/src/features/admin/`, `frontend/src/routes/` |
| **Votre branche** | `oumar` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 1 | 2 |
| Sprint 1 | 4 | 3 |
| Sprint 2 | 2 | 2 |
| Sprint 3 | 2 | 2 |
| Phase pilote | 0 | 3 |
| Tâches transversales (tous les sprints) | 1 | 2 |
| **Total** | **10** | **14** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-11** : Initialiser les projets back-end et front-end
  - Côté : Front-end · Dossier : `frontend/`
  - Livrable : Squelettes fonctionnels
  - Appui : Nzemkam

#### 🤝 Vous êtes en appui

- [ ] **S0-09** : Définir la charte graphique et les composants de base
  - Responsable : Angue · Côté : Front-end · Livrable : Charte graphique
- [ ] **S0-10** : Réaliser les wireframes et maquettes
  - Responsable : Angue · Côté : Front-end · Livrable : Maquettes validées

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-10** : Pages d'inscription et de connexion
  - Côté : Front-end · Dossier : `frontend/src/features/auth/`
  - Livrable : Écrans fonctionnels
  - Appui : Angue
- [ ] **S1-11** : Catalogue, fiche produit, recherche et filtres (interface)
  - Côté : Front-end · Dossier : `frontend/src/features/catalog/`
  - Livrable : Pages catalogue
  - Appui : Angue
- [ ] **S1-12** : Formulaire de publication de produit (vendeur)
  - Côté : Front-end · Dossier : `frontend/src/features/seller/products/`
  - Livrable : Formulaire opérationnel
  - Appui : Angue
- [ ] **S1-13** : Validation des formulaires et gestion des erreurs
  - Côté : Front-end · Dossier : `frontend/src/lib/`
  - Livrable : Messages d'erreur clairs
  - Appui : Angue

#### 🤝 Vous êtes en appui

- [ ] **S1-07** : Composants d'interface réutilisables (boutons, cartes produit, formulaires)
  - Responsable : Angue · Côté : Front-end · Livrable : Bibliothèque de composants
- [ ] **S1-08** : Page d'accueil, navigation et menu mobile
  - Responsable : Angue · Côté : Front-end · Livrable : Accueil responsive
- [ ] **S1-09** : Pages de profil vendeur et acheteur (interface)
  - Responsable : Angue · Côté : Front-end · Livrable : Pages de profil

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-09** : Interface d'administration et de signalement
  - Côté : Front-end · Dossier : `frontend/src/features/admin/`
  - Livrable : Pages admin
  - Appui : Angue
- [ ] **S2-10** : PWA : manifeste, mise en cache et mode hors ligne de base
  - Côté : Front-end · Dossier : `frontend/ (vite.config, public/, service worker)`
  - Livrable : Application installable
  - Appui : Angue

#### 🤝 Vous êtes en appui

- [ ] **S2-07** : Interface du tableau de bord vendeur
  - Responsable : Angue · Côté : Front-end · Livrable : Page tableau de bord
- [ ] **S2-08** : Graphiques de suivi (ventes par produit, niveau de stock)
  - Responsable : Angue · Côté : Front-end · Livrable : Graphiques intégrés

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-09** : Panier et tunnel de commande (interface)
  - Côté : Front-end · Dossier : `frontend/src/features/cart/ et frontend/src/features/orders/`
  - Livrable : Pages panier et paiement
  - Appui : Angue
- [ ] **S3-13** : Prix du marché de référence (optionnel, si le temps le permet)
  - Côté : Front-end · Dossier : `frontend/src/pages/ (prix du marché)`
  - Livrable : Page prix du marché
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S3-10** : Suivi de commande et notifications (interface)
  - Responsable : Angue · Côté : Front-end · Livrable : Pages de suivi
- [ ] **S3-11** : Avis et notation des vendeurs (interface)
  - Responsable : Angue · Côté : Front-end · Livrable : Composant d'avis

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### 🤝 Vous êtes en appui

- [ ] **P-05** : Corriger les anomalies prioritaires
  - Responsable : Nzemkam · Côté : Front-end · Livrable : Version corrigée
- [ ] **P-06** : Préparer la présentation et la démonstration finale
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Soutenance
- [ ] **P-07** : Rétrospective finale et bilan du projet
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Bilan de projet

### Tâches transversales (tous les sprints)

_Objectif : faire vivre la méthode Scrum et la qualité tout au long du projet._

#### ✅ Vous êtes responsable

- [ ] **T-04** : Présenter les fonctionnalités terminées
  - Côté : Front-end · Dossier : `Sprint Review (démonstration)`
  - Livrable : Sprint Review
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **T-03** : Relire les Pull Requests (revue de code)
  - Responsable : Nzemkam · Côté : Front-end · Livrable : En continu
- [ ] **T-05** : Déclarer et suivre les anomalies
  - Responsable : Mengue, Bouga · Côté : QA · Livrable : Tickets suivis

---

## 🧰 Boîte à outils et règles

- **Stack** : React 19, Vite 8, React Router 7, Axios, TanStack Query 5, React Hook Form + Zod 4, Tailwind CSS 4, Recharts 3, vite-plugin-pwa 2, Vitest 5.
- **Tests** : Vitest + Testing Library pour les composants et formulaires critiques.
- **Méthode** : mobile first (largeur 360 px), textes en français, composants réutilisables de `components/ui/`, appels API via le client Axios commun, états de chargement et d'erreur toujours traités.
- **Accessibilité** : zones tactiles de 44 px minimum, libellés sur tous les champs, contrastes suffisants.
- **Références** : `docs/03-architecture.md` (routes front, liste des endpoints), `docs/design/` (maquettes et charte graphique).

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
