# 🧪 MENGUE MBIAM Eliance

**QA-testeuse** · Projet AgriElevage Ambam

> Votre fichier de tâches personnel. Cochez les cases au fur et à mesure (`- [x]`) et gardez ce fichier à jour dans votre branche. Les identifiants de tâche (S1-04, etc.) sont à reprendre dans vos branches et vos Pull Requests.

---

## 🎯 Votre mission

Définir la stratégie de test et garantir la qualité fonctionnelle de chaque livrable.

## 🗂️ Fiche

| | |
|---|---|
| **Rôle** | QA-testeuse |
| **Domaine** | QA |
| **Dossiers de travail** | `docs/tests/`, `GitHub Issues (anomalies)` |
| **Votre branche** | `eliance` : vous poussez **uniquement** sur cette branche, jamais sur `main`, `develop` ou la branche d'un autre (voir [CONTRIBUTING.md](../../../CONTRIBUTING.md)) |

## 📊 Résumé de votre charge

| Phase | Responsable | En appui |
|-------|:-----------:|:--------:|
| Sprint 0 | 1 | 0 |
| Sprint 1 | 1 | 1 |
| Sprint 2 | 2 | 2 |
| Sprint 3 | 1 | 0 |
| Phase pilote | 1 | 2 |
| Tâches transversales (tous les sprints) | 1 | 0 |
| **Total** | **7** | **5** |

---

## 🧱 Vos tâches par sprint

### Sprint 0 : Préparation

_Objectif : poser les bases (backlog, étude de marché, maquettes, architecture, environnement)._

#### ✅ Vous êtes responsable

- [ ] **S0-13** : Définir la stratégie et le plan de tests
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Plan de tests
  - Appui : Bouga

### Sprint 1 : Comptes et catalogue

_Objectif : un utilisateur peut s'inscrire et se connecter, et un vendeur peut publier des produits consultables._

#### ✅ Vous êtes responsable

- [ ] **S1-15** : Rédiger les cas de test (comptes, catalogue)
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Cas de test
  - Appui : —

#### 🤝 Vous êtes en appui

- [ ] **S1-16** : Tests API et tests exploratoires
  - Responsable : Bouga · Côté : QA · Livrable : Rapport de tests

### Sprint 2 : Tableau de bord, administration et tests

_Objectif : le vendeur suit son activité, l'administrateur contrôle la plateforme et la qualité est consolidée._

#### ✅ Vous êtes responsable

- [ ] **S2-13** : Tests fonctionnels et d'interface
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport de tests
  - Appui : Bouga
- [ ] **S2-14** : Tests d'accessibilité et de lisibilité sur mobile
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport d'accessibilité
  - Appui : Angue

#### 🤝 Vous êtes en appui

- [ ] **S2-12** : Tests unitaires et d'intégration du back-end
  - Responsable : Simo, Nzemkam · Côté : Back-end · Livrable : Suite de tests automatisés
- [ ] **S2-15** : Tests de performance et de non-régression (Sprint 1)
  - Responsable : Bouga · Côté : QA · Livrable : Rapport de non-régression

> ⚠️ **Point d'attention** : les commandes n'existent qu'au Sprint 3. Le tableau de bord du Sprint 2 s'appuiera donc sur des données de ventes simulées (jeu de données de test), à remplacer par les vraies données au Sprint 3.

### Sprint 3 : Commande et paiement

_Objectif : un acheteur peut commander et payer, et le vendeur est notifié._

#### ✅ Vous êtes responsable

- [ ] **S3-15** : Tests de bout en bout et non-régression
  - Côté : QA · Dossier : `docs/tests/`
  - Livrable : Rapport final de tests
  - Appui : Bouga

### Phase pilote

_Objectif : tester la plateforme avec un petit groupe de producteurs et d'acheteurs à Ambam._

#### ✅ Vous êtes responsable

- [ ] **P-04** : Collecter les retours et mesurer l'usage (questionnaire, indicateurs)
  - Côté : QA · Dossier : `docs/pilote/`
  - Livrable : Rapport de retours
  - Appui : Bouga, Souop

#### 🤝 Vous êtes en appui

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
