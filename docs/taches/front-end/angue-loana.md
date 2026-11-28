# 🎨 ANGUE Loana

**Développeuse front-end, UX/UI** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Concevoir l'identité visuelle et les maquettes, puis construire les composants et pages à forte dimension UX (accueil, profils, tableau de bord, suivi de commande, avis).

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Développeuse front-end, UX/UI |
| **Domaine** | Front-end |
| **Dossiers de travail** | `docs/design/`, `frontend/src/components/`, `frontend/src/styles/`, `frontend/src/features/seller/dashboard/`, `frontend/src/features/orders/`, `frontend/src/features/reviews/` |
| **Votre branche** | `loana` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 2 | 0 |
| Sprint 1 | 3 | 4 |
| Sprint 2 | 2 | 3 |
| Sprint 3 | 3 | 2 |
| Phase pilote | 0 | 4 |
| Tâches transversales (tous les sprints) | 1 | 2 |
| **Total** | **11** | **15** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-09** : Définir la charte graphique et les composants de base
  - Côté : Front-end · Dossier : `frontend/src/styles/ et docs/design/`
  - Livrable : Charte graphique
  - Appui : Abba
- [ ] **S0-10** : Réaliser les wireframes et maquettes
  - Côté : Front-end · Dossier : `docs/design/`
  - Livrable : Maquettes validées
  - Appui : Abba

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-07** : Composants d'interface réutilisables (boutons, cartes produit, formulaires)
  - Côté : Front-end · Dossier : `frontend/src/components/ui/`
  - Livrable : Bibliothèque de composants
  - Appui : Abba
- [ ] **S1-08** : Page d'accueil, navigation et menu mobile
  - Côté : Front-end · Dossier : `frontend/src/components/layout/ et frontend/src/pages/`
  - Livrable : Accueil responsive
  - Appui : Abba
- [ ] **S1-09** : Pages de profil vendeur et acheteur (interface)
  - Côté : Front-end · Dossier : `frontend/src/features/auth/ et frontend/src/pages/`
  - Livrable : Pages de profil
  - Appui : Abba

#### 🤝 Vous êtes en appui

- [ ] **S1-10** : Pages d'inscription et de connexion
  - Responsable : Abba · Côté : Front-end · Livrable : Écrans fonctionnels
- [ ] **S1-11** : Catalogue, fiche produit, recherche et filtres (interface)
  - Responsable : Abba · Côté : Front-end · Livrable : Pages catalogue
- [ ] **S1-12** : Formulaire de publication de produit (vendeur)
  - Responsable : Abba · Côté : Front-end · Livrable : Formulaire opérationnel
- [ ] **S1-13** : Validation des formulaires et gestion des erreurs
  - Responsable : Abba · Côté : Front-end · Livrable : Messages d'erreur clairs

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-07** : Interface du tableau de bord vendeur
  - Côté : Front-end · Dossier : `frontend/src/features/seller/dashboard/`
  - Livrable : Page tableau de bord
  - Appui : Abba
- [ ] **S2-08** : Graphiques de suivi (ventes par produit, niveau de stock)
  - Côté : Front-end · Dossier : `frontend/src/features/seller/dashboard/`
  - Livrable : Graphiques intégrés
  - Appui : Abba

#### 🤝 Vous êtes en appui

- [ ] **S2-09** : Interface d'administration et de signalement
  - Responsable : Abba · Côté : Front-end · Livrable : Pages admin
- [ ] **S2-10** : PWA : manifeste, mise en cache et mode hors ligne de base
  - Responsable : Abba · Côté : Front-end · Livrable : Application installable
- [ ] **S2-14** : Tests d'accessibilité et de lisibilité sur mobile
  - Responsable : Mengue · Côté : QA · Livrable : Rapport d'accessibilité

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-10** : Suivi de commande et notifications (interface)
  - Côté : Front-end · Dossier : `frontend/src/features/orders/`
  - Livrable : Pages de suivi
  - Appui : Abba
- [ ] **S3-11** : Avis et notation des vendeurs (interface)
  - Côté : Front-end · Dossier : `frontend/src/features/reviews/`
  - Livrable : Composant d'avis
  - Appui : Abba
- [ ] **S3-12** : Brancher le tableau de bord sur les vraies commandes
  - Côté : Front-end · Dossier : `frontend/src/features/seller/dashboard/`
  - Livrable : Tableau de bord alimenté
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S3-09** : Panier et tunnel de commande (interface)
  - Responsable : Abba · Côté : Front-end · Livrable : Pages panier et paiement
- [ ] **S3-18** : Guide d'utilisation en français (texte et captures)
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Guide utilisateur

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### 🤝 Vous êtes en appui

- [ ] **P-02** : Former les utilisateurs et les accompagner
  - Responsable : Souop, Gildas · Côté : Client · Livrable : Sessions de formation
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
