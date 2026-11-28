# 🛠️ NZEMKAM F. Laura S.

**Lead Developer** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Définir l'architecture, construire le cœur de l'API (sécurité, catalogue, paiement, notifications, modération) et garantir la qualité du code par la revue.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Lead Developer |
| **Domaine** | Back-end |
| **Dossiers de travail** | `backend/ (toutes les applications, revue de code)`, `docs/03-architecture.md`, `docs/02-stack-technologique.md` |
| **Votre branche** | `laura` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 2 | 5 |
| Sprint 1 | 4 | 3 |
| Sprint 2 | 5 | 2 |
| Sprint 3 | 4 | 7 |
| Phase pilote | 1 | 2 |
| Tâches transversales (tous les sprints) | 2 | 1 |
| **Total** | **18** | **20** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-07** : Concevoir l'architecture et le modèle de données
  - Côté : Back-end · Dossier : `docs/03-architecture.md`
  - Livrable : Schéma d'architecture, MCD
  - Appui : Simo
- [ ] **S0-08** : Valider CamPay (bac à sable), lancer les demandes de compte de production et de nom d'expéditeur SMS
  - Côté : Back-end · Dossier : `docs/02-stack-technologique.md`
  - Livrable : Note de choix technique
  - Appui : Simo

#### 🤝 Vous êtes en appui

- [ ] **S0-04** : Définir la Definition of Done et les conventions Git
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Document de conventions
- [ ] **S0-05** : Créer le dépôt GitHub, les branches, l'intégration continue
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Dépôt configuré
- [ ] **S0-06** : Identifier les risques et préparer un plan de mitigation
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Registre des risques
- [ ] **S0-11** : Initialiser les projets back-end et front-end
  - Responsable : Simo (back), Abba (front) · Côté : Back-end · Livrable : Squelettes fonctionnels
- [ ] **S0-12** : Configurer PostgreSQL et le fichier .env.example
  - Responsable : Simo · Côté : Back-end · Livrable : Base et configuration prêtes

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-03** : Permissions par rôle et sécurité de base (hachage, validation)
  - Côté : Back-end · Dossier : `backend/apps/common/ et backend/apps/accounts/`
  - Livrable : Accès contrôlés par rôle
  - Appui : Simo
- [ ] **S1-04** : Modèles catégories, unités (kg, pièce, lot) et produits, CRUD, upload de photos
  - Côté : Back-end · Dossier : `backend/apps/catalog/`
  - Livrable : API produits
  - Appui : Simo
- [ ] **S1-05** : Recherche et filtres du catalogue (API)
  - Côté : Back-end · Dossier : `backend/apps/catalog/ (filters.py)`
  - Livrable : Endpoint filtré
  - Appui : —
- [ ] **S1-06** : Documentation de l'API (Swagger/OpenAPI)
  - Côté : Back-end · Dossier : `backend/config/ (drf-spectacular)`
  - Livrable : Documentation interactive
  - Appui : Simo

#### 🤝 Vous êtes en appui

- [ ] **S1-01** : Modèles utilisateurs et rôles, authentification JWT
  - Responsable : Simo · Côté : Back-end · Livrable : API inscription et connexion
- [ ] **S1-02** : Profils vendeur et acheteur (API)
  - Responsable : Simo · Côté : Back-end · Livrable : API profils
- [ ] **S1-14** : Déployer un environnement de test
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : URL de test

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-04** : Back-office : validation des vendeurs, modération des annonces
  - Côté : Back-end · Dossier : `backend/apps/moderation/`
  - Livrable : Module d'administration
  - Appui : Simo
- [ ] **S2-05** : Gestion des signalements et des litiges
  - Côté : Back-end · Dossier : `backend/apps/moderation/`
  - Livrable : Module de signalement
  - Appui : Simo
- [ ] **S2-06** : Journalisation et historique des actions d'administration
  - Côté : Back-end · Dossier : `backend/apps/moderation/ (AuditLog)`
  - Livrable : Journal d'audit
  - Appui : —
- [ ] **S2-11** : Revue de sécurité (bonnes pratiques OWASP)
  - Côté : Back-end · Dossier : `backend/ et docs/tests/`
  - Livrable : Rapport de sécurité
  - Appui : Bouga
- [ ] **S2-12** : Tests unitaires et d'intégration du back-end
  - Côté : Back-end · Dossier : `backend/apps/*/tests/`
  - Livrable : Suite de tests automatisés
  - Appui : Mengue

#### 🤝 Vous êtes en appui

- [ ] **S2-01** : API du tableau de bord vendeur (stock, ventes)
  - Responsable : Simo · Côté : Back-end · Livrable : Endpoints statistiques
- [ ] **S2-02** : Alertes de stock bas
  - Responsable : Simo · Côté : Back-end · Livrable : Notifications de stock

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-06** : Intégration du paiement Mobile Money
  - Côté : Back-end · Dossier : `backend/apps/payments/`
  - Livrable : Module de paiement
  - Appui : Simo
- [ ] **S3-07** : Gestion des paiements échoués et des remboursements
  - Côté : Back-end · Dossier : `backend/apps/payments/`
  - Livrable : Cas d'erreur traités
  - Appui : Simo
- [ ] **S3-08** : Notifications (SMS Orange) et suivi de commande
  - Côté : Back-end · Dossier : `backend/apps/notifications/`
  - Livrable : Service de notifications
  - Appui : Simo
- [ ] **S3-13** : Prix du marché de référence (optionnel, si le temps le permet)
  - Côté : Back-end · Dossier : `backend/apps/catalog/ (market_prices)`
  - Livrable : Page prix du marché
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S3-01** : Panier, commande et gestion du stock (API)
  - Responsable : Simo · Côté : Back-end · Livrable : API commandes
- [ ] **S3-02** : Statuts de commande (en attente, confirmée, livrée, annulée)
  - Responsable : Simo · Côté : Back-end · Livrable : Workflow de commande
- [ ] **S3-03** : Options de retrait ou de livraison et frais associés
  - Responsable : Simo · Côté : Back-end · Livrable : Gestion de la livraison
- [ ] **S3-05** : Avis et notation des vendeurs (API)
  - Responsable : Simo · Côté : Back-end · Livrable : API avis
- [ ] **S3-14** : Tests de paiement (environnement bac à sable)
  - Responsable : Bouga · Côté : QA · Livrable : Rapport de tests paiement
- [ ] **S3-16** : Tests de charge sur les parcours critiques
  - Responsable : Bouga · Côté : QA · Livrable : Rapport de charge
- [ ] **S3-19** : Déploiement en production, sauvegardes de la base, documentation finale
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Application en ligne

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### ✅ Vous êtes responsable

- [ ] **P-05** : Corriger les anomalies prioritaires
  - Côté : Back-end · Dossier : `backend/ (selon l'anomalie)`
  - Livrable : Version corrigée
  - Appui : Simo, Abba, Angue

#### 🤝 Vous êtes en appui

- [ ] **P-06** : Préparer la présentation et la démonstration finale
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Soutenance
- [ ] **P-07** : Rétrospective finale et bilan du projet
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Bilan de projet

### Tâches transversales (tous les sprints)

_Objectif : faire vivre la méthode Scrum et la qualité tout au long du projet._

#### ✅ Vous êtes responsable

- [ ] **T-03** : Relire les Pull Requests (revue de code)
  - Côté : Back-end · Dossier : `Pull Requests GitHub`
  - Livrable : En continu
  - Appui : Simo, Abba, Angue
- [ ] **T-04** : Présenter les fonctionnalités terminées
  - Côté : Back-end · Dossier : `Sprint Review (démonstration)`
  - Livrable : Sprint Review
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **T-05** : Déclarer et suivre les anomalies
  - Responsable : Mengue, Bouga · Côté : QA · Livrable : Tickets suivis

---

## 🧰 Boîte à outils et règles

- **Stack** : Python 3.12+, Django 5.2 LTS, Django REST Framework 3.18, SimpleJWT, django-filter, drf-spectacular, PostgreSQL (Neon), CamPay, Orange SMS, Cloudinary.
- **Tests** : pytest + pytest-django + factory_boy ; viser au moins 70 % de couverture sur le code que vous écrivez.
- **Méthode** : décrire d'abord le contrat de l'API (routes, champs, erreurs) dans Swagger, puis prévenir les développeurs front concernés ; logique métier dans `services.py`, vues fines.
- **Sécurité** : permissions par rôle et par propriétaire testées, aucune donnée sensible dans les logs, secrets dans `.env`.
- **Références** : `docs/03-architecture.md` (modèle de données, routes API, cycle de commande), `docs/04-requirements.md`.

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
