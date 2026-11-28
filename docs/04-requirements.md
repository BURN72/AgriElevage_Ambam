# 📋 Requirements du projet

Ce document liste les exigences fonctionnelles et non fonctionnelles de la plateforme **AgriElevage Ambam**.

**Priorités (MoSCoW)** : **M** = Must (indispensable), **S** = Should (important), **C** = Could (souhaitable, si le temps le permet).
**Cibles chiffrées** : propositions à valider en équipe.

---

## 1. Exigences fonctionnelles

### 1.1 Comptes et profils (Sprint 1)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-01 | Un visiteur peut créer un compte avec son téléphone (et un email optionnel) et choisir son rôle : acheteur ou vendeur | M |
| EF-02 | Un utilisateur peut se connecter et se déconnecter ; la session est maintenue par jetons JWT avec rafraîchissement | M |
| EF-03 | Un utilisateur peut demander la réinitialisation de son mot de passe | S |
| EF-04 | Un utilisateur peut consulter et modifier son profil (nom, téléphone, localité) | M |
| EF-05 | Un vendeur renseigne un profil vendeur (nom d'exploitation, type : individuel, GIC ou coopérative, localité, description) soumis à validation | M |
| EF-06 | Les accès sont contrôlés par rôle (acheteur, vendeur, administrateur) et par propriétaire | M |

### 1.2 Catalogue (Sprint 1)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-07 | Les produits sont classés par catégories (cultures, élevage, sous-catégories) | M |
| EF-08 | Un vendeur validé publie un produit : nom, description, catégorie, prix, unité (kg, pièce, lot), quantité disponible, localité, date limite de disponibilité | M |
| EF-09 | Un vendeur ajoute jusqu'à 5 photos par produit ; les images sont contrôlées (type, taille) et redimensionnées | M |
| EF-10 | Un vendeur peut modifier, désactiver ou supprimer ses produits | M |
| EF-11 | Tout visiteur consulte le catalogue paginé | M |
| EF-12 | Tout visiteur recherche par texte, filtre (catégorie, prix, localité, vendeur) et trie (prix, date) | M |
| EF-13 | Tout visiteur consulte la fiche détaillée d'un produit et le profil public du vendeur | M |
| EF-14 | Un produit dont le stock est épuisé ou la date limite dépassée n'est plus proposé à l'achat | S |

### 1.3 Tableau de bord vendeur (Sprint 2)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-15 | Le vendeur voit un résumé : produits actifs, nombre de commandes, revenus de la période (données simulées au Sprint 2, réelles au Sprint 3) | M |
| EF-16 | Le vendeur visualise ses ventes par période et par produit sous forme de graphiques | S |
| EF-17 | Le vendeur est alerté lorsque le stock d'un produit passe sous un seuil | S |
| EF-18 | Le vendeur exporte ses ventes en CSV (PDF en option) | C |

### 1.4 Administration et modération (Sprint 2)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-19 | L'administrateur liste les vendeurs par statut et peut les valider, rejeter ou suspendre | M |
| EF-20 | L'administrateur peut masquer ou rétablir une annonce | M |
| EF-21 | Un utilisateur connecté peut signaler un produit ou un vendeur avec un motif | S |
| EF-22 | L'administrateur traite et clôt les signalements | S |
| EF-23 | Les actions d'administration sont enregistrées dans un journal d'audit consultable | S |

### 1.5 Application web installable (Sprint 2)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-24 | L'application est installable (PWA) ; l'interface et les pages déjà consultées restent accessibles hors ligne, avec un message clair lorsque le réseau est requis | S |

### 1.6 Panier et commandes (Sprint 3)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-25 | L'acheteur ajoute des produits au panier, modifie les quantités, retire des lignes ; le panier est conservé sur l'appareil | M |
| EF-26 | La validation du panier crée une commande par vendeur | M |
| EF-27 | Le stock est vérifié et décrémenté à la commande, puis restitué en cas d'annulation ou d'expiration | M |
| EF-28 | Une commande suit les statuts : en attente de paiement, confirmée, en préparation, prête, livrée, annulée | M |
| EF-29 | L'acheteur peut annuler une commande avant sa préparation ; le vendeur peut annuler avec un motif | M |
| EF-30 | L'acheteur choisit retrait sur place ou livraison ; les frais dépendent de la zone | S |
| EF-31 | Acheteur et vendeur consultent l'historique et le suivi de leurs commandes | M |
| EF-32 | L'acheteur ou le vendeur télécharge un reçu au format PDF | C |

### 1.7 Paiement (Sprint 3)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-33 | L'acheteur paie par Mobile Money (MTN MoMo, Orange Money) via CamPay | M |
| EF-34 | L'acheteur peut choisir le paiement à la livraison, confirmé par le vendeur | M |
| EF-35 | Les confirmations de paiement du prestataire sont reçues par webhook, avec vérification de signature et traitement idempotent | M |
| EF-36 | Les paiements échoués ou expirés sont gérés (statut, nouvelle tentative, restitution du stock) | M |
| EF-37 | L'administrateur peut déclencher un remboursement | S |
| EF-38 | La commission de la plateforme est calculée et enregistrée pour chaque commande (taux à définir) | S |

### 1.8 Notifications et avis (Sprint 3)

| ID | Exigence | Priorité |
|----|----------|:--------:|
| EF-39 | Les utilisateurs reçoivent des notifications dans l'application (nouvelle commande, changement de statut, validation de profil) | S |
| EF-40 | Les événements clés déclenchent un SMS (Orange) et proposent un lien WhatsApp de contact (commande reçue, paiement confirmé, commande prête) | S |
| EF-41 | Après livraison, l'acheteur note le vendeur (1 à 5) et peut laisser un commentaire ; la note moyenne s'affiche sur le profil vendeur | S |
| EF-42 | Les prix du marché de référence sont consultables par produit | C |

---

## 2. Exigences non fonctionnelles

### 2.1 Performance

| ID | Exigence | Cible |
|----|----------|-------|
| ENF-01 | Chargement des pages principales sur connexion 3G | moins de 3 secondes |
| ENF-02 | Temps de réponse de l'API pour les lectures courantes | moins de 500 ms au 95e centile |
| ENF-03 | Images de liste optimisées | moins de 200 Ko par image affichée |
| ENF-04 | Listes paginées | 20 éléments par page par défaut |

### 2.2 Sécurité

| ID | Exigence |
|----|----------|
| ENF-05 | Tout le trafic en production passe par HTTPS |
| ENF-06 | Les mots de passe sont stockés hachés, jamais en clair |
| ENF-07 | Les jetons d'accès ont une durée courte ; les jetons de rafraîchissement sont invalidés à la déconnexion |
| ENF-08 | Toutes les entrées sont validées côté serveur ; protection contre injections SQL, XSS et CSRF |
| ENF-09 | Limitation de débit sur la connexion, l'inscription et le paiement |
| ENF-10 | Les secrets (clés API, clé Django) sont hors du dépôt, dans des variables d'environnement |
| ENF-11 | Aucune donnée sensible de paiement (code secret, données de carte) n'est stockée |
| ENF-12 | Les permissions par rôle et par propriétaire sont couvertes par des tests automatisés |

### 2.3 Utilisabilité et accessibilité

| ID | Exigence |
|----|----------|
| ENF-13 | Interface entièrement en français, avec un vocabulaire simple |
| ENF-14 | Conception mobile first, utilisable dès 360 px de large |
| ENF-15 | Zones tactiles d'au moins 44 px, contrastes suffisants, champs avec libellés |
| ENF-16 | Le parcours de commande comporte un nombre minimal d'étapes (panier, livraison, paiement, confirmation) |
| ENF-17 | Les erreurs sont expliquées en langage clair avec une action proposée |

### 2.4 Compatibilité

| ID | Exigence |
|----|----------|
| ENF-18 | Fonctionnement sur les navigateurs mobiles récents : Chrome Android, Firefox, Safari iOS |
| ENF-19 | Fonctionnement sur ordinateur (Chrome, Firefox, Edge) |

### 2.5 Fiabilité et données

| ID | Exigence |
|----|----------|
| ENF-20 | Les opérations de commande et de stock sont atomiques (transactions) |
| ENF-21 | Les paiements sont idempotents et réconciliables avec le prestataire |
| ENF-22 | Sauvegardes régulières de la base de production, restauration testée avant le pilote |
| ENF-23 | Disponibilité visée pendant le pilote : 99 % (indicatif, offres gratuites) |

### 2.6 Maintenabilité et qualité

| ID | Exigence | Cible |
|----|----------|-------|
| ENF-24 | Couverture des tests back-end | au moins 70 % |
| ENF-25 | Lint et formatage vérifiés par l'intégration continue | à chaque Pull Request |
| ENF-26 | API documentée en OpenAPI/Swagger | à jour à chaque sprint |
| ENF-27 | Revue de code obligatoire avant fusion | 1 relecteur minimum |
| ENF-28 | Code en anglais, interface en français, conventions Git respectées | |

### 2.7 Juridique et conformité

| ID | Exigence |
|----|----------|
| ENF-29 | Conditions générales d'utilisation et mentions légales accessibles |
| ENF-30 | Consentement explicite à la collecte des données personnelles, collecte minimale (réglementation camerounaise à vérifier) |
| ENF-31 | Les conditions de commission et de remboursement sont affichées avant le paiement |

---

## 3. Exigences de données

| ID | Exigence |
|----|----------|
| ED-01 | Le numéro de téléphone est unique par compte |
| ED-02 | Les montants sont stockés en entiers (FCFA, sans décimales) |
| ED-03 | Les dates sont stockées en UTC et affichées en heure locale (UTC+1) |
| ED-04 | Le prix unitaire est copié dans chaque ligne de commande |
| ED-05 | Les suppressions de produits liés à des commandes sont logiques (désactivation), pas physiques |

---

## 4. Contraintes et hypothèses

| ID | Contrainte ou hypothèse |
|----|-------------------------|
| C-01 | Hébergement sur offres gratuites ou à faible coût pour le MVP |
| C-02 | CamPay (retenu) fournit un environnement de test ; la demande de compte de production est faite au Sprint 0 |
| C-03 | Le paiement à la livraison sert de solution de repli |
| C-04 | La durée des sprints est fixée à 2 semaines |
| C-05 | Les utilisateurs disposent d'un smartphone et d'un compte Mobile Money |

---

## 5. Synthèse par sprint

| Sprint | Exigences couvertes |
|--------|---------------------|
| Sprint 0 | Cadrage, ENF-25, ENF-26 (mise en place), choix techniques |
| Sprint 1 | EF-01 à EF-14, ENF-06, ENF-07, ENF-12 |
| Sprint 2 | EF-15 à EF-24, ENF-08 à ENF-11, ENF-15, tests unitaires et d'intégration |
| Sprint 3 | EF-25 à EF-42, ENF-20, ENF-21, ENF-31 |
| Pilote | Validation des objectifs O1 à O5, retours utilisateurs |
