# 🤝 SOUOP KUATE Donald

**Représentant client** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Représenter les besoins des utilisateurs, clarifier les priorités métier et valider chaque sprint par une recette.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | Représentant client |
| **Domaine** | Client |
| **Dossiers de travail** | `docs/recettes/`, `docs/pilote/` |
| **Votre branche** | `donald` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 2 | 1 |
| Sprint 1 | 1 | 0 |
| Sprint 2 | 1 | 0 |
| Sprint 3 | 1 | 0 |
| Phase pilote | 3 | 3 |
| Tâches transversales (tous les sprints) | 1 | 1 |
| **Total** | **9** | **5** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-02** : Finaliser l'étude de marché, le persona et l'analyse de la concurrence
  - Côté : Client · Dossier : `docs/`
  - Livrable : Dossier d'étude de marché
  - Appui : Gildas
- [ ] **S0-03** : Recueillir et valider les besoins des utilisateurs
  - Côté : Client · Dossier : `docs/`
  - Livrable : Liste de besoins validée
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **S0-01** : Rédiger la vision, les user stories et le backlog initial
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Product backlog priorisé

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-17** : Recette côté client
  - Côté : Client · Dossier : `docs/recettes/`
  - Livrable : PV de recette Sprint 1
  - Appui : —

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-16** : Recette côté client
  - Côté : Client · Dossier : `docs/recettes/`
  - Livrable : PV de recette Sprint 2
  - Appui : —

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-17** : Recette finale côté client
  - Côté : Client · Dossier : `docs/recettes/`
  - Livrable : PV de recette Sprint 3
  - Appui : —

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### ✅ Vous êtes responsable

- [ ] **P-01** : Organiser le pilote et recruter les producteurs testeurs
  - Côté : Client · Dossier : `docs/pilote/`
  - Livrable : Liste des participants
  - Appui : Gildas
- [ ] **P-02** : Former les utilisateurs et les accompagner
  - Côté : Client · Dossier : `docs/pilote/`
  - Livrable : Sessions de formation
  - Appui : Angue
- [ ] **P-03** : Assurer le support pendant le pilote (téléphone, WhatsApp)
  - Côté : Client · Dossier : `docs/pilote/`
  - Livrable : Journal des demandes
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **P-04** : Collecter les retours et mesurer l'usage (questionnaire, indicateurs)
  - Responsable : Mengue · Côté : QA · Livrable : Rapport de retours
- [ ] **P-06** : Préparer la présentation et la démonstration finale
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Soutenance
- [ ] **P-07** : Rétrospective finale et bilan du projet
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Bilan de projet

### Tâches transversales (tous les sprints)

_Objectif : faire vivre la méthode Scrum et la qualité tout au long du projet._

#### ✅ Vous êtes responsable

- [ ] **T-06** : Valider les priorités métier
  - Côté : Client · Dossier : `Sprint Planning`
  - Livrable : Sprint Planning
  - Appui : Gildas

#### 🤝 Vous êtes en appui

- [ ] **T-01** : Mettre à jour le backlog et le tableau Kanban
  - Responsable : Gildas · Côté : Gestion de projet · Livrable : Après chaque réunion

---

## 🧰 Boîte à outils et règles

- **Rôle** : porter la voix des vendeurs et des acheteurs, trancher les priorités métier avec le Product Owner.
- **Méthode** : recette à la fin de chaque sprint avec un PV signé dans `docs/recettes/` ; retours écrits et priorisés.
- **Références** : persona et parcours clés du cahier des charges, critères de recette.

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
