# 🗒️ Fichiers de tâches individuels

Chaque membre de l'équipe dispose de son fichier avec la liste de ses tâches, classées par sprint, avec leur identifiant, leur côté (front-end ou back-end), les dossiers concernés et le livrable attendu.

> Le Product Owner étant l'enseignant, il n'a pas de fichier.

| Membre | Rôle | Fichier | Responsable de | En appui sur |
|--------|------|---------|:--------------:|:------------:|
| SEGNING WOUATI Gildas | Scrum Master | [scrum-master/gildas-segning.md](scrum-master/gildas-segning.md) | 14 | 6 |
| NZEMKAM F. Laura S. | Lead Developer | [back-end/nzemkam-laura.md](back-end/nzemkam-laura.md) | 18 | 20 |
| SIMO MOKAM Stella | Développeuse back-end | [back-end/simo-stella.md](back-end/simo-stella.md) | 15 | 15 |
| ABBA Oumar | Développeur front-end | [front-end/abba-oumar.md](front-end/abba-oumar.md) | 10 | 14 |
| ANGUE Loana | Développeuse front-end, UX/UI | [front-end/angue-loana.md](front-end/angue-loana.md) | 11 | 15 |
| SOUOP KUATE Donald | Représentant client | [client/souop-donald.md](client/souop-donald.md) | 9 | 5 |
| MENGUE MBIAM Eliance | QA-testeuse | [qa/mengue-eliance.md](qa/mengue-eliance.md) | 7 | 5 |
| BOUGA NIAMPOU Hermann | QA-testeur | [qa/bouga-hermann.md](qa/bouga-hermann.md) | 5 | 7 |

## Organisation

- **Back-end** : [Nzemkam](back-end/nzemkam-laura.md) (Lead Developer), [Simo](back-end/simo-stella.md)
- **Front-end** : [Abba](front-end/abba-oumar.md), [Angue](front-end/angue-loana.md)
- **Gestion de projet** : [Gildas](scrum-master/gildas-segning.md)
- **Client** : [Souop](client/souop-donald.md)
- **QA** : [Mengue](qa/mengue-eliance.md), [Bouga](qa/bouga-hermann.md)

## Identifiants de tâche

| Préfixe | Phase |
|---------|-------|
| S0-xx | Sprint 0 : Préparation |
| S1-xx | Sprint 1 : Comptes et catalogue |
| S2-xx | Sprint 2 : Tableau de bord, administration et tests |
| S3-xx | Sprint 3 : Commande et paiement |
| P-xx | Phase pilote |
| T-xx | Tâches transversales |

## Coordination front-end / back-end

- Le back-end publie le contrat de chaque endpoint dans Swagger **avant** de le coder ; le front-end s'appuie dessus (données simulées si l'endpoint n'est pas prêt).
- Les dépendances principales : S1-01 à S1-05 (back) alimentent S1-10 à S1-12 (front) ; S3-01 à S3-08 (back) alimentent S3-09 à S3-11 (front).
- En cas de changement de contrat, prévenir tout de suite les personnes concernées et mettre à jour la documentation.
