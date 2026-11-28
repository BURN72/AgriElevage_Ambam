# 🧪 BOUGA NIAMPOU Hermann

**QA-testeur** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Tester l'API, explorer les cas limites, vérifier la sécurité, la charge et la non-régression.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | QA-testeur |
| **Domaine** | QA |
| **Dossiers de travail** | `docs/tests/`, `Collection Postman ou Insomnia`, `GitHub Issues (anomalies)` |
| **Votre branche** | `hermann` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 0 | 1 |
| Sprint 1 | 1 | 0 |
| Sprint 2 | 1 | 2 |
| Sprint 3 | 2 | 1 |
| Phase pilote | 0 | 3 |
| Tâches transversales (tous les sprints) | 1 | 0 |
| **Total** | **5** | **7** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### 🤝 Vous êtes en appui

- [ ] **S0-13** : Définir la stratégie et le plan de tests
  - Responsable : Mengue · Côté : QA · Livrable : Plan de tests

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-16** : Tests API et tests exploratoires
  - Côté : QA · Dossier : `docs/tests/ et collection Postman`
  - Livrable : Rapport de tests
  - Appui : Mengue

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-15** : Tests de performance et de non-régression (Sprint 1)
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport de non-régression
  - Appui : Mengue

#### 🤝 Vous êtes en appui

- [ ] **S2-11** : Revue de sécurité (bonnes pratiques OWASP)
  - Responsable : Nzemkam · Côté : Back-end · Livrable : Rapport de sécurité
- [ ] **S2-13** : Tests fonctionnels et d'interface
  - Responsable : Mengue · Côté : QA · Livrable : Rapport de tests

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-14** : Tests de paiement (environnement bac à sable)
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport de tests paiement
  - Appui : Nzemkam
- [ ] **S3-16** : Tests de charge sur les parcours critiques
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport de charge
  - Appui : Nzemkam

#### 🤝 Vous êtes en appui

- [ ] **S3-15** : Tests de bout en bout et non-régression
  - Responsable : Mengue · Côté : QA · Livrable : Rapport final de tests

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

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

- [ ] **T-05** : Déclarer et suivre les anomalies
  - Côté : QA · Dossier : `GitHub Issues`
  - Livrable : Tickets suivis
  - Appui : Développeurs

---

## 🧰 Boîte à outils et règles

- **Outils** : Swagger UI, Postman ou Insomnia, GitHub Issues, pytest et Vitest (lecture des résultats), outils de test d'accessibilité du navigateur.
- **Méthode** : cas de test rédigés à partir des exigences (`docs/04-requirements.md`) ; chaque anomalie est ouverte comme Issue avec étapes de reproduction, résultat attendu, résultat obtenu et capture.
- **Rapports** : un rapport par sprint dans `docs/tests/` (cas passés, échoués, anomalies ouvertes).
- **Références** : critères de recette du cahier des charges, Definition of Done.

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
