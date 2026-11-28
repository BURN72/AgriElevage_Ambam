# 🛠️ SIMO MOKAM Stella

**Développeuse back-end** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Développer l'API des comptes, des commandes et du tableau de bord, en binôme avec la Lead Developer.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Développeuse back-end |
| **Domaine** | Back-end |
| **Dossiers de travail** | `backend/apps/accounts/`, `backend/apps/orders/`, `backend/apps/dashboard/`, `backend/apps/reviews/`, `backend/apps/deliveries/` |
| **Votre branche** | `stella` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 2 | 2 |
| Sprint 1 | 2 | 3 |
| Sprint 2 | 4 | 2 |
| Sprint 3 | 6 | 3 |
| Phase pilote | 0 | 3 |
| Tâches transversales (tous les sprints) | 1 | 2 |
| **Total** | **15** | **15** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-11** : Initialiser les projets back-end et front-end
  - Côté : Back-end · Dossier : `backend/`
  - Livrable : Squelettes fonctionnels
  - Appui : Nzemkam
- [ ] **S0-12** : Configurer PostgreSQL et le fichier .env.example
  - Côté : Back-end · Dossier : `backend/config/settings/, .env.example, docker-compose.yml`
  - Livrable : Base et configuration prêtes
  - Appui : Nzemkam

#### 🤝 Vous êtes en appui

- [ ] **S0-07** : Concevoir l'architecture et le modèle de données
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Schéma d'architecture, MCD
- [ ] **S0-08** : Valider CamPay (bac à sable), lancer les demandes de compte de production et de nom d'expéditeur SMS
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Note de choix technique

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-01** : Modèles utilisateurs et rôles, authentification JWT
  - Côté : Back-end · Dossier : `backend/apps/accounts/`
  - Livrable : API inscription et connexion
  - Appui : Nzemkam
- [ ] **S1-02** : Profils vendeur et acheteur (API)
  - Côté : Back-end · Dossier : `backend/apps/accounts/`
  - Livrable : API profils
  - Appui : Nzemkam

#### 🤝 Vous êtes en appui

- [ ] **S1-03** : Permissions par rôle et sécurité de base (hachage, validation)
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Accès contrôlés par rôle
- [ ] **S1-04** : Modèles catégories, unités (kg, pièce, lot) et produits, CRUD, upload de photos
  - Responsable : Nzemkam · Côté : Back-end · Livrable : API produits
- [ ] **S1-06** : Documentation de l'API (Swagger/OpenAPI)
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Documentation interactive

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-01** : API du tableau de bord vendeur (stock, ventes)
  - Côté : Back-end · Dossier : `backend/apps/dashboard/`
  - Livrable : Endpoints statistiques
  - Appui : Nzemkam
- [ ] **S2-02** : Alertes de stock bas
  - Côté : Back-end · Dossier : `backend/apps/dashboard/ et backend/apps/notifications/`
  - Livrable : Notifications de stock
  - Appui : Nzemkam
- [ ] **S2-03** : Export des ventes (CSV ou PDF)
  - Côté : Back-end · Dossier : `backend/apps/dashboard/`
  - Livrable : Export téléchargeable
  - Appui : —
- [ ] **S2-12** : Tests unitaires et d'intégration du back-end
  - Côté : Back-end · Dossier : `backend/apps/*/tests/`
  - Livrable : Suite de tests automatisés
  - Appui : Mengue

#### 🤝 Vous êtes en appui

- [ ] **S2-04** : Back-office : validation des vendeurs, modération des annonces
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Module d'administration
- [ ] **S2-05** : Gestion des signalements et des litiges
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Module de signalement

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-01** : Panier, commande et gestion du stock (API)
  - Côté : Back-end · Dossier : `backend/apps/orders/`
  - Livrable : API commandes
  - Appui : Nzemkam
- [ ] **S3-02** : Statuts de commande (en attente, confirmée, livrée, annulée)
  - Côté : Back-end · Dossier : `backend/apps/orders/`
  - Livrable : Workflow de commande
  - Appui : Nzemkam
- [ ] **S3-03** : Options de retrait ou de livraison et frais associés
  - Côté : Back-end · Dossier : `backend/apps/deliveries/`
  - Livrable : Gestion de la livraison
  - Appui : Nzemkam
- [ ] **S3-04** : Génération d'un reçu ou d'une facture PDF
  - Côté : Back-end · Dossier : `backend/apps/orders/ (reçus PDF)`
  - Livrable : Reçu téléchargeable
  - Appui : —
- [ ] **S3-05** : Avis et notation des vendeurs (API)
  - Côté : Back-end · Dossier : `backend/apps/reviews/`
  - Livrable : API avis
  - Appui : Nzemkam
- [ ] **S3-12** : Brancher le tableau de bord sur les vraies commandes
  - Côté : Back-end · Dossier : `backend/apps/dashboard/`
  - Livrable : Tableau de bord alimenté
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S3-06** : Intégration du paiement Mobile Money
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Module de paiement
- [ ] **S3-07** : Gestion des paiements échoués et des remboursements
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Cas d'erreur traités
- [ ] **S3-08** : Notifications (SMS Orange) et suivi de commande
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Service de notifications

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### 🤝 Vous êtes en appui

- [ ] **P-05** : Corriger les anomalies prioritaires
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Version corrigée
- [ ] **P-06** : Préparer la présentation et la démonstration finale
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Soutenance
- [ ] **P-07** : Rétrospective finale et bilan du projet
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Bilan de projet

### Tâches transversales (tous les sprints)

_Objectif : faire vivre la méthode Scrum et la qualité tout au long du projet._

#### ✅ Vous êtes responsable

- [ ] **T-04** : Présenter les fonctionnalités terminées
  - Côté : Back-end · Dossier : `Sprint Review (démonstration)`
  - Livrable : Sprint Review
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **T-03** : Relire les Pull Requests (revue de code)
  - Responsable : Nzemkam · Côté : Back-end · Livrable : En continu
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
