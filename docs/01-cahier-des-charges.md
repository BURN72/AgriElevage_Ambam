# 📘 Cahier des charges : AgriElevage Ambam

| | |
|---|---|
| **Projet** | AgriElevage Ambam : plateforme de vente de produits agricoles et d'élevage |
| **Cadre** | Cours GSI 712, méthode Scrum |
| **Version** | 1.0 (brouillon à valider par le Product Owner) |
| **Date** | Novembre 2026 |
| **Rédaction** | Équipe projet (coordination : Scrum Master) |

> Le nom « AgriElevage Ambam » est provisoire. Les valeurs chiffrées marquées « cible » sont des propositions à valider en équipe.

---

## 1. Présentation du projet

### 1.1 Contexte

Ambam est le chef-lieu du département de la Vallée-du-Ntem (région du Sud, Cameroun), à proximité des frontières avec le Gabon et la Guinée équatoriale. L'économie locale repose largement sur l'agriculture (cacao, plantain, manioc, arachide, palmier à huile) et sur un petit élevage (volaille, porcs, caprins). La position de carrefour commercial de la ville offre un potentiel de vente vers les marchés voisins.

### 1.2 Problématique

Les petits producteurs et éleveurs rencontrent plusieurs difficultés :

- des prix imposés par des intermédiaires ;
- des pertes importantes après récolte (stockage, transport, écoulement tardif) ;
- peu de visibilité sur la demande et sur les prix du marché ;
- un accès limité à de nouveaux acheteurs (commerçants, restaurants, ménages, marchés voisins) ;
- peu de suivi écrit de leur activité.

### 1.3 Solution proposée

**AgriElevage Ambam** est une plateforme web de vente en ligne, conçue mobile first, légère et utilisable avec une connexion faible. Elle permet :

- aux **vendeurs** (producteurs, éleveurs, GIC) de publier leurs produits, gérer leur stock et leurs commandes ;
- aux **acheteurs** de découvrir les produits locaux, commander et payer, notamment par Mobile Money ;
- aux **administrateurs** de valider les vendeurs et de modérer la plateforme.

### 1.4 Objectifs

| N° | Objectif | Indicateur de succès (cible) |
|----|----------|------------------------------|
| O1 | Permettre à un vendeur de publier et gérer ses produits en autonomie | 15 vendeurs inscrits et validés pendant le pilote |
| O2 | Mettre en relation vendeurs et acheteurs sans intermédiaire obligatoire | 30 produits publiés, 20 commandes passées pendant le pilote |
| O3 | Proposer un paiement adapté au contexte local | Paiement Mobile Money fonctionnel de bout en bout |
| O4 | Rester utilisable sur smartphone d'entrée de gamme et connexion faible | Chargement des pages principales en moins de 3 s sur 3G (cible) |
| O5 | Valider la solution sur le terrain | Pilote à Ambam avec retours collectés et analysés |

### 1.5 Objectifs de développement durable

| ODD | Contribution |
|-----|--------------|
| **ODD 2 : Faim « zéro »** | Meilleur accès à une alimentation locale, agriculture durable |
| ODD 1 : Pas de pauvreté | Meilleurs revenus pour les petits producteurs |
| ODD 8 : Travail décent et croissance économique | Emplois ruraux, commerce local |
| ODD 12 : Consommation et production responsables | Réduction des pertes et du gaspillage |
| ODD 9 : Industrie, innovation et infrastructure | Outil numérique pour le monde rural |

---

## 2. Périmètre

### 2.1 Inclus dans le projet

- Comptes utilisateurs avec trois rôles : acheteur, vendeur, administrateur.
- Catalogue de produits avec photos, recherche et filtres.
- Panier, commande et suivi de commande.
- Paiement par Mobile Money et paiement à la livraison.
- Retrait sur place ou livraison avec frais par zone.
- Notifications (dans l'application, SMS ; lien WhatsApp de contact).
- Tableau de bord vendeur (stock, ventes).
- Back-office d'administration et modération.
- Avis et notation des vendeurs.
- Application web installable (PWA) avec mode hors ligne de base.
- Pilote avec un petit groupe d'utilisateurs à Ambam.

### 2.2 Hors périmètre (versions futures)

- Application mobile native (Android ou iOS).
- Carnet complet de suivi des cultures et du cheptel.
- Vente transfrontalière (douane, devises, fiscalité).
- Messagerie instantanée entre acheteurs et vendeurs.
- Flotte de livraison propre à la plateforme.
- Enchères, abonnements, programme de fidélité.

---

## 3. Parties prenantes

| Partie prenante | Rôle dans le projet |
|-----------------|---------------------|
| **Product Owner** (enseignant) | Définit la vision, priorise le backlog, valide les revues de sprint |
| **Équipe projet** (8 personnes, voir tableau ci-dessous) | Conçoit, développe, teste et livre la plateforme |
| **Vendeurs** (producteurs, éleveurs, GIC) | Utilisateurs principaux, publient et vendent |
| **Acheteurs** (ménages, commerçants, restaurants) | Utilisateurs, commandent et paient |
| **Administrateurs** | Valident les vendeurs, modèrent, traitent les litiges |

### Équipe

| Membre | Rôle Scrum | Domaine |
|--------|------------|---------|
| SEGNING WOUATI Gildas | Scrum Master | Animation, suivi, Git/CI, documentation, déploiement |
| NZEMKAM F. Laura S. | Lead Developer | Architecture, back-end (cœur, paiement), revue de code |
| SIMO MOKAM Stella | Développeuse | Back-end (comptes, commandes, tableau de bord) |
| ABBA Oumar | Développeur | Front-end (authentification, catalogue, panier) |
| ANGUE Loana | Développeuse | Front-end, UX/UI, maquettes |
| SOUOP KUATE Donald | Représentant client | Besoins, priorités métier, recette |
| MENGUE MBIAM Eliance | QA-testeuse | Plan de tests, tests fonctionnels |
| BOUGA NIAMPOU Hermann | QA-testeur | Tests API, tests exploratoires, non-régression |

---

## 4. Utilisateurs cibles et personas

### Persona 1 : le vendeur

**Pascal Ondoua, 38 ans, planteur-éleveur près d'Ambam**
- **Activité** : 3 ha (cacao, plantain, manioc), 40 poules et 10 porcs.
- **Équipement** : smartphone Android d'entrée de gamme, WhatsApp, Mobile Money.
- **Besoins** : trouver des acheteurs fiables, savoir à quel prix vendre, éviter les pertes.
- **Frustrations** : intermédiaires qui fixent les prix, aucun suivi écrit, peu de conseils techniques.
- **Attentes** : application en français, simple, rapide, payable et utilisable avec Mobile Money.

### Persona 2 : l'acheteuse

**Chantal Mballa, 34 ans, gérante d'un restaurant à Ambam** (profil fictif)
- **Besoins** : s'approvisionner régulièrement en produits frais (plantain, manioc, volaille) à prix connu.
- **Frustrations** : prix variables, qualité irrégulière, déplacements au marché.
- **Attentes** : voir les produits avec photos et prix, commander depuis son téléphone, payer par Mobile Money, être prévenue quand la commande est prête.

---

## 5. Description fonctionnelle

### 5.1 Modules

| Code | Module | Description | Sprint |
|------|--------|-------------|--------|
| M1 | Comptes et profils | Inscription, connexion, profils acheteur et vendeur, rôles | 1 |
| M2 | Catalogue | Catégories, produits, photos, recherche, filtres | 1 |
| M3 | Tableau de bord vendeur | Résumé, ventes, stock bas, export | 2 |
| M4 | Administration et modération | Validation des vendeurs, signalements, journal d'audit | 2 |
| M5 | PWA | Application installable, mode hors ligne de base | 2 |
| M6 | Commandes | Panier, commande, statuts, annulation, reçu | 3 |
| M7 | Paiement | Mobile Money, paiement à la livraison, webhooks, remboursements | 3 |
| M8 | Livraison et retrait | Options, zones, frais | 3 |
| M9 | Notifications | In-app, SMS (lien WhatsApp de contact) | 3 |
| M10 | Avis | Notation des vendeurs après livraison | 3 |
| M11 | Prix du marché (optionnel) | Prix de référence par produit | 3 |

Le détail des exigences figure dans [04-requirements.md](04-requirements.md).

### 5.2 Parcours clés

**Parcours vendeur : publier un produit**
1. Le vendeur s'inscrit et complète son profil vendeur.
2. L'administrateur valide le profil.
3. Le vendeur crée une annonce (nom, catégorie, prix, unité, quantité, localité, photos).
4. Le produit apparaît dans le catalogue et se met à jour selon le stock.

**Parcours acheteur : commander et payer**
1. L'acheteur parcourt le catalogue, filtre et ouvre une fiche produit.
2. Il ajoute des produits au panier et choisit retrait ou livraison.
3. Il valide la commande (une commande est créée par vendeur).
4. Il paie par Mobile Money (ou choisit le paiement à la livraison).
5. Il reçoit des notifications et suit le statut jusqu'à la livraison.
6. Il note le vendeur.

**Parcours administrateur : modérer**
1. L'administrateur consulte les vendeurs en attente et les valide ou rejette.
2. Il traite les signalements et peut masquer une annonce.
3. Il consulte le journal d'audit de ses actions.

---

## 6. Contraintes

| Type | Contrainte |
|------|------------|
| **Réseau et terminaux** | Connexion irrégulière, smartphones Android d'entrée de gamme : pages légères, images optimisées, cache |
| **Paiement** | Intégration via **CamPay** (MTN MoMo, Orange Money) ; tests en bac à sable avant toute mise en production ; compte marchand de production à faire valider (demande au Sprint 0) |
| **Langue** | Interface entièrement en français, vocabulaire simple |
| **Budget** | Hébergement sur offres gratuites (Cloudflare Pages, Render, Neon, Cloudinary) ; limitations connues : mise en veille de l'API après 15 min (réveil d'environ 1 min), base de 1 Go, 25 crédits Cloudinary par mois |
| **Équipe et délais** | Équipe étudiante de 8 personnes, sprints de **2 semaines**, contraintes de calendrier académique |
| **Juridique** | Respect de la loi n° 2024/017 sur la protection des données personnelles (en vigueur depuis le 23 juin 2026 : consentement explicite et révocable, minimisation, droits d'accès et de suppression, transferts hors du pays encadrés) et de la loi n° 2010/021 sur le commerce électronique ; conditions générales, politique de confidentialité et mentions légales. Points externes à confirmer : voir [06-registre-des-decisions.md](06-registre-des-decisions.md) |
| **Qualité** | Revue de code obligatoire, tests automatisés, validation du client à chaque sprint |

### Hypothèses

- Les vendeurs et acheteurs disposent d'un smartphone et d'un compte Mobile Money.
- CamPay fournit un environnement de test (bac à sable) et valide le compte marchand de production avant le pilote.
- L'hébergement gratuit suffit pour le volume du pilote.

---

## 7. Livrables

| Livrable | Description |
|----------|-------------|
| Dépôt GitHub | Code source back-end et front-end, documentation |
| Cahier des charges, architecture, requirements | Dossier de conception (ce dossier `docs/`) |
| Maquettes et charte graphique | Écrans validés par le client |
| Application déployée | Environnement de test puis de production |
| Documentation de l'API | Interface Swagger/OpenAPI |
| Rapports de tests et PV de recette | Un par sprint |
| Guide d'utilisation en français | Pour vendeurs et acheteurs |
| Rapport de pilote et bilan | Retours terrain et leçons apprises |

---

## 8. Planning prévisionnel

| Phase | Objectif |
|-------|----------|
| **Sprint 0** | Backlog, étude de marché, maquettes, architecture, environnement |
| **Sprint 1** | Comptes et catalogue |
| **Sprint 2** | Tableau de bord, administration et tests |
| **Sprint 3** | Commande et paiement |
| **Pilote** | Test avec un groupe de producteurs et d'acheteurs à Ambam |

> Point d'attention : le tableau de bord du Sprint 2 utilise des données de ventes simulées, car les commandes n'existent qu'au Sprint 3. Il est branché sur les vraies commandes au Sprint 3.

Le détail des tâches figure dans [05-repartition-des-taches.md](05-repartition-des-taches.md) et dans les fichiers individuels du dossier [taches](taches/README.md).

---

## 9. Risques

| Risque | Probabilité | Impact | Mesure |
|--------|-------------|--------|--------|
| Accès tardif ou refusé à l'API Mobile Money | Moyenne | Fort | CamPay retenu ; demande de compte de production dès le Sprint 0, développement sur bac à sable, prévoir le paiement à la livraison comme solution de repli |
| Sprint 3 trop chargé | Forte | Moyen | Marquer les tâches optionnelles, prioriser le MVP, déplacer des tâches lors du Sprint Planning |
| Faible adoption par les producteurs | Moyenne | Fort | Interface très simple, formation, accompagnement pendant le pilote |
| Connexion internet insuffisante | Forte | Moyen | PWA, images légères, cache, messages d'erreur clairs |
| Indisponibilité de membres (examens, imprévus) | Moyenne | Moyen | Binômes sur les tâches critiques, revue de code croisée |
| Limites de l'hébergement gratuit (veille, quotas) | Moyenne | Moyen | Message de chargement, cache PWA, informer le pilote ; offre payante d'entrée de gamme pour l'API si nécessaire |
| Failles de sécurité | Faible | Fort | Revue OWASP au Sprint 2, secrets hors dépôt, tests de sécurité |
| Dérive du périmètre | Moyenne | Moyen | Backlog géré par le Product Owner, changements validés en Sprint Planning |

---

## 10. Critères de recette

Le projet est accepté lorsque :

- [ ] un vendeur peut s'inscrire, être validé et publier un produit avec photos ;
- [ ] un acheteur peut rechercher, filtrer, commander et payer (Mobile Money en bac à sable, paiement à la livraison) ;
- [ ] le stock est mis à jour correctement et les statuts de commande suivent le cycle défini ;
- [ ] le vendeur consulte un tableau de bord avec des données réelles ;
- [ ] l'administrateur peut valider un vendeur, masquer une annonce et consulter le journal d'audit ;
- [ ] l'application est installable, utilisable sur mobile en français et supporte une coupure de connexion de base ;
- [ ] les tests automatisés passent et les rapports de recette de chaque sprint sont signés par le client ;
- [ ] la documentation (README, API, guide d'utilisation) est livrée.

---

## 11. Glossaire

| Terme | Définition |
|-------|------------|
| **GIC** | Groupe d'initiative commune (association de producteurs) |
| **MVP** | Version minimale du produit, suffisante pour être testée |
| **PWA** | Application web installable, utilisable partiellement hors ligne |
| **Mobile Money** | Paiement par téléphone (MTN MoMo, Orange Money) |
| **Webhook** | Appel envoyé par le prestataire de paiement à notre serveur pour confirmer un paiement |
| **JWT** | Jeton signé servant à authentifier un utilisateur |
| **Backlog** | Liste priorisée des fonctionnalités à développer |
| **Definition of Done** | Critères qu'une tâche doit remplir pour être considérée terminée |
| **Recette** | Validation des livrables par le client |

---

## 12. Documents associés

- [02-stack-technologique.md](02-stack-technologique.md)
- [03-architecture.md](03-architecture.md)
- [04-requirements.md](04-requirements.md)
- [05-repartition-des-taches.md](05-repartition-des-taches.md)
- [taches/README.md](taches/README.md)
- [06-registre-des-decisions.md](06-registre-des-decisions.md)
- [07-etude-de-marche.md](07-etude-de-marche.md)

## 13. Propriété intellectuelle

Le projet est protégé par une **licence propriétaire : tous droits réservés au groupe projet** (voir [LICENSE](../LICENSE)). Le dépôt reste privé et n'accepte que des dépendances à licence permissive. Les règles éventuelles de l'établissement sur la propriété des travaux d'étudiants sont à confirmer auprès de l'enseignant (décision D-19).
