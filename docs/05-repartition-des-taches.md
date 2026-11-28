# 📋 Répartition des tâches par sprint

Projet **AgriElevage Ambam**. Méthode : Scrum (cours GSI 712). Le Product Owner étant l'enseignant, il n'apparaît pas dans la répartition.

> Proposition de départ, à ajuster en équipe lors du Sprint Planning. Durée d'un sprint : 2 semaines. Les fichiers individuels sont dans [taches/](taches/README.md).

## 👥 Équipe et rôles

| Membre | Rôle Scrum | Domaine principal |
|--------|------------|-------------------|
| **SEGNING WOUATI Gildas** | Scrum Master | Animation, suivi, Git/CI, documentation, déploiement |
| **NZEMKAM F. Laura S.** | Lead Developer | Architecture, back-end (cœur, paiement), revue de code |
| **SIMO MOKAM Stella** | Développeuse | Back-end (comptes, commandes, tableau de bord) |
| **ABBA Oumar** | Développeur | Front-end (authentification, catalogue, panier) |
| **ANGUE Loana** | Développeuse | Front-end, UX/UI, maquettes |
| **SOUOP KUATE Donald** | Représentant client | Besoins, priorités métier, recette |
| **MENGUE MBIAM Eliance** | QA-testeuse | Plan de tests, tests fonctionnels |
| **BOUGA NIAMPOU Hermann** | QA-testeur | Tests API, tests exploratoires, non-régression |

## 🔁 Cérémonies (à chaque sprint)

| Cérémonie | Animateur | Participants | Durée indicative |
|---|---|---|---|
| Sprint Planning | Gildas | Toute l'équipe + Product Owner | 1 à 2 h |
| Daily Scrum | Gildas | Équipe de développement et QA | 15 min |
| Sprint Review | Gildas | Toute l'équipe + Product Owner + client | 1 h |
| Rétrospective | Gildas | Équipe | 45 min |

---

## 🧱 Sprint 0 : Préparation

**Objectif** : poser les bases (backlog, étude de marché, maquettes, architecture, environnement).

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| S0-01 | Rédiger la vision, les user stories et le backlog initial | Gildas | Souop | Product backlog priorisé |
| S0-02 | Finaliser l'étude de marché, le persona et l'analyse de la concurrence | Souop | Gildas | Dossier d'étude de marché |
| S0-03 | Recueillir et valider les besoins des utilisateurs | Souop | Gildas | Liste de besoins validée |
| S0-04 | Définir la Definition of Done et les conventions Git | Gildas | Nzemkam | Document de conventions |
| S0-05 | Créer le dépôt GitHub, les branches, l'intégration continue | Gildas | Nzemkam | Dépôt configuré |
| S0-06 | Identifier les risques et préparer un plan de mitigation | Gildas | Nzemkam | Registre des risques |
| S0-07 | Concevoir l'architecture et le modèle de données | Nzemkam | Simo | Schéma d'architecture, MCD |
| S0-08 | Valider CamPay (bac à sable), lancer les demandes de compte de production et de nom d'expéditeur SMS | Nzemkam | Simo | Note de choix technique |
| S0-09 | Définir la charte graphique et les composants de base | Angue | Abba | Charte graphique |
| S0-10 | Réaliser les wireframes et maquettes | Angue | Abba | Maquettes validées |
| S0-11 | Initialiser les projets back-end et front-end | Simo (back), Abba (front) | Nzemkam | Squelettes fonctionnels |
| S0-12 | Configurer PostgreSQL et le fichier .env.example | Simo | Nzemkam | Base et configuration prêtes |
| S0-13 | Définir la stratégie et le plan de tests | Mengue | Bouga | Plan de tests |
| S0-14 | Rédiger le README | Gildas |  | README.md |

---

## 🔐 Sprint 1 : Comptes et catalogue

**Objectif** : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables.

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| S1-01 | Modèles utilisateurs et rôles, authentification JWT | Simo | Nzemkam | API inscription et connexion |
| S1-02 | Profils vendeur et acheteur (API) | Simo | Nzemkam | API profils |
| S1-03 | Permissions par rôle et sécurité de base (hachage, validation) | Nzemkam | Simo | Accès contrôlés par rôle |
| S1-04 | Modèles catégories, unités (kg, pièce, lot) et produits, CRUD, upload de photos | Nzemkam | Simo | API produits |
| S1-05 | Recherche et filtres du catalogue (API) | Nzemkam |  | Endpoint filtré |
| S1-06 | Documentation de l'API (Swagger/OpenAPI) | Nzemkam | Simo | Documentation interactive |
| S1-07 | Composants d'interface réutilisables (boutons, cartes produit, formulaires) | Angue | Abba | Bibliothèque de composants |
| S1-08 | Page d'accueil, navigation et menu mobile | Angue | Abba | Accueil responsive |
| S1-09 | Pages de profil vendeur et acheteur (interface) | Angue | Abba | Pages de profil |
| S1-10 | Pages d'inscription et de connexion | Abba | Angue | Écrans fonctionnels |
| S1-11 | Catalogue, fiche produit, recherche et filtres (interface) | Abba | Angue | Pages catalogue |
| S1-12 | Formulaire de publication de produit (vendeur) | Abba | Angue | Formulaire opérationnel |
| S1-13 | Validation des formulaires et gestion des erreurs | Abba | Angue | Messages d'erreur clairs |
| S1-14 | Déployer un environnement de test | Gildas | Nzemkam | URL de test |
| S1-15 | Rédiger les cas de test (comptes, catalogue) | Mengue |  | Cas de test |
| S1-16 | Tests API et tests exploratoires | Bouga | Mengue | Rapport de tests |
| S1-17 | Recette côté client | Souop |  | PV de recette Sprint 1 |

---

## 📊 Sprint 2 : Tableau de bord, administration et tests

**Objectif** : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée.

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| S2-01 | API du tableau de bord vendeur (stock, ventes) | Simo | Nzemkam | Endpoints statistiques |
| S2-02 | Alertes de stock bas | Simo | Nzemkam | Notifications de stock |
| S2-03 | Export des ventes (CSV ou PDF) | Simo |  | Export téléchargeable |
| S2-04 | Back-office : validation des vendeurs, modération des annonces | Nzemkam | Simo | Module d'administration |
| S2-05 | Gestion des signalements et des litiges | Nzemkam | Simo | Module de signalement |
| S2-06 | Journalisation et historique des actions d'administration | Nzemkam |  | Journal d'audit |
| S2-07 | Interface du tableau de bord vendeur | Angue | Abba | Page tableau de bord |
| S2-08 | Graphiques de suivi (ventes par produit, niveau de stock) | Angue | Abba | Graphiques intégrés |
| S2-09 | Interface d'administration et de signalement | Abba | Angue | Pages admin |
| S2-10 | PWA : manifeste, mise en cache et mode hors ligne de base | Abba | Angue | Application installable |
| S2-11 | Revue de sécurité (bonnes pratiques OWASP) | Nzemkam | Bouga | Rapport de sécurité |
| S2-12 | Tests unitaires et d'intégration du back-end | Simo, Nzemkam | Mengue | Suite de tests automatisés |
| S2-13 | Tests fonctionnels et d'interface | Mengue | Bouga | Rapport de tests |
| S2-14 | Tests d'accessibilité et de lisibilité sur mobile | Mengue | Angue | Rapport d'accessibilité |
| S2-15 | Tests de performance et de non-régression (Sprint 1) | Bouga | Mengue | Rapport de non-régression |
| S2-16 | Recette côté client | Souop |  | PV de recette Sprint 2 |
| S2-17 | Mise à jour de la documentation et de l'environnement de test | Gildas |  | Documentation à jour |

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

---

## 💳 Sprint 3 : Commande et paiement

**Objectif** : un acheteur peut commander et payer, et le vendeur est notifié.

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| S3-01 | Panier, commande et gestion du stock (API) | Simo | Nzemkam | API commandes |
| S3-02 | Statuts de commande (en attente, confirmée, livrée, annulée) | Simo | Nzemkam | Workflow de commande |
| S3-03 | Options de retrait ou de livraison et frais associés | Simo | Nzemkam | Gestion de la livraison |
| S3-04 | Génération d'un reçu ou d'une facture PDF | Simo |  | Reçu téléchargeable |
| S3-05 | Avis et notation des vendeurs (API) | Simo | Nzemkam | API avis |
| S3-06 | Intégration du paiement Mobile Money | Nzemkam | Simo | Module de paiement |
| S3-07 | Gestion des paiements échoués et des remboursements | Nzemkam | Simo | Cas d'erreur traités |
| S3-08 | Notifications (SMS Orange) et suivi de commande | Nzemkam | Simo | Service de notifications |
| S3-09 | Panier et tunnel de commande (interface) | Abba | Angue | Pages panier et paiement |
| S3-10 | Suivi de commande et notifications (interface) | Angue | Abba | Pages de suivi |
| S3-11 | Avis et notation des vendeurs (interface) | Angue | Abba | Composant d'avis |
| S3-12 | Brancher le tableau de bord sur les vraies commandes | Simo, Angue |  | Tableau de bord alimenté |
| S3-13 | Prix du marché de référence (optionnel, si le temps le permet) | Nzemkam, Abba |  | Page prix du marché |
| S3-14 | Tests de paiement (environnement bac à sable) | Bouga | Nzemkam | Rapport de tests paiement |
| S3-15 | Tests de bout en bout et non-régression | Mengue | Bouga | Rapport final de tests |
| S3-16 | Tests de charge sur les parcours critiques | Bouga | Nzemkam | Rapport de charge |
| S3-17 | Recette finale côté client | Souop |  | PV de recette Sprint 3 |
| S3-18 | Guide d'utilisation en français (texte et captures) | Gildas | Angue | Guide utilisateur |
| S3-19 | Déploiement en production, sauvegardes de la base, documentation finale | Gildas | Nzemkam | Application en ligne |

---

## 🌱 Phase pilote

**Objectif** : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam.

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| P-01 | Organiser le pilote et recruter les producteurs testeurs | Souop | Gildas | Liste des participants |
| P-02 | Former les utilisateurs et les accompagner | Souop, Gildas | Angue | Sessions de formation |
| P-03 | Assurer le support pendant le pilote (téléphone, WhatsApp) | Souop | Gildas | Journal des demandes |
| P-04 | Collecter les retours et mesurer l'usage (questionnaire, indicateurs) | Mengue | Bouga, Souop | Rapport de retours |
| P-05 | Corriger les anomalies prioritaires | Nzemkam | Simo, Abba, Angue | Version corrigée |
| P-06 | Préparer la présentation et la démonstration finale | Gildas | Toute l'équipe | Soutenance |
| P-07 | Rétrospective finale et bilan du projet | Gildas | Toute l'équipe | Bilan de projet |

---

## 🔄 Tâches transversales (tous les sprints)

**Objectif** : faire vivre la méthode Scrum et la qualité tout au long du projet.

| ID | Tâche | Responsable | Appui | Livrable |
|----|-------|-------------|-------|----------|
| T-01 | Mettre à jour le backlog et le tableau Kanban | Gildas | Souop | Après chaque réunion |
| T-02 | Rédiger le compte rendu de sprint et suivre l'avancement (burndown) | Gildas |  | Fin de sprint |
| T-03 | Relire les Pull Requests (revue de code) | Nzemkam | Simo, Abba, Angue | En continu |
| T-04 | Présenter les fonctionnalités terminées | Chaque développeur | Gildas | Sprint Review |
| T-05 | Déclarer et suivre les anomalies | Mengue, Bouga | Développeurs | Tickets suivis |
| T-06 | Valider les priorités métier | Souop | Gildas | Sprint Planning |

---

## ✅ Definition of Done (proposition)

Une tâche est terminée lorsque :

- [ ] le code est relu par au moins un autre membre (Pull Request approuvée) ;
- [ ] les tests automatisés passent ;
- [ ] la fonctionnalité a été testée par la QA ;
- [ ] elle est déployée sur l'environnement de test ;
- [ ] elle a été validée par le représentant client ;
- [ ] la documentation concernée est à jour.
