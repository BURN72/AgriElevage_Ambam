# AGENTS.md : instructions pour les agents IA

Ce fichier guide tout agent de code (Cursor, Claude Code, Copilot, etc.) qui travaille sur **AgriElevage Ambam**. Lis-le en entier avant de modifier le dépôt.

---

## 1. Le projet en bref

Plateforme web de vente directe de produits agricoles et d'élevage à Ambam (Cameroun). Trois rôles : **acheteur**, **vendeur**, **administrateur**. Fonctions : catalogue, panier, commande, paiement Mobile Money et à la livraison, retrait ou livraison, notifications, tableau de bord vendeur, modération, avis, PWA.

**Contexte d'usage** : smartphones Android d'entrée de gamme, connexion faible ou irrégulière, utilisateurs peu à l'aise avec le numérique. Chaque choix doit rester **simple, léger et en français**.

Projet étudiant en **Scrum** (cours GSI 712). Le Product Owner est l'enseignant.

## 2. Documents de référence (source de vérité)

Avant de coder, consulte le document concerné. En cas de conflit entre une demande et ces documents, **signale-le** au lieu de trancher seul.

| Sujet | Document |
|-------|----------|
| Besoins, périmètre, parcours | `docs/01-cahier-des-charges.md` |
| Technologies | `docs/02-stack-technologique.md` |
| Architecture, modèle de données, routes API, rôles, cycle de commande | `docs/03-architecture.md` |
| Exigences (EF-xx, ENF-xx) | `docs/04-requirements.md` |
| Tâches et responsables | `docs/05-repartition-des-taches.md` et `docs/taches/` |
| Branches, commits, PR | `CONTRIBUTING.md` |

## 3. Stack

| Couche | Technologie |
|--------|-------------|
| Front-end | React 19, Vite 8, React Router 7, Axios, TanStack Query 5, React Hook Form + Zod 4, Tailwind CSS 4, Recharts 3, vite-plugin-pwa 2, Vitest 5 |
| Back-end | Python 3.12+, Django 5.2 LTS, Django REST Framework 3.18, SimpleJWT, django-filter, drf-spectacular, PostgreSQL (Neon). Paiement : CamPay (Mobile Money). SMS : Orange. Images : Cloudinary. Hébergement : Cloudflare Pages, Render, Neon |
| Base | PostgreSQL |
| Tests | pytest + pytest-django + factory_boy (back), Vitest + Testing Library (front) |
| Qualité | Ruff + Black (Python), ESLint + Prettier (JS) |
| CI | GitHub Actions |

Les versions exactes sont provisoires. **N'ajoute pas de dépendance** sans l'expliquer et sans l'accord de l'équipe.

## 4. Structure du dépôt

```
backend/
  config/settings/          base.py, dev.py, prod.py, test.py
  apps/                     accounts, catalog, orders, payments, deliveries,
                            reviews, notifications, dashboard, moderation, common
frontend/src/
  api/ components/{ui,layout}/ features/{auth,catalog,cart,orders,reviews,seller,admin}/
  hooks/ lib/ pages/ routes/ styles/ tests/
docs/                       documentation, maquettes (design/), tests/, recettes/, pilote/
```

Chaque application Django contient `models.py`, `serializers.py`, `views.py`, `urls.py`, `services.py`, `permissions.py` (si besoin) et `tests/`.
Le front est organisé **par fonctionnalité** (`features/`).

## 5. Commandes

> Disponibles une fois les projets initialisés (tâche S0-11).

```bash
# Back-end
cd backend
python -m venv venv && source venv/bin/activate
pip install -r requirements-dev.txt
python manage.py migrate
python manage.py runserver        # http://localhost:8000
pytest                            # tests
ruff check . && black --check .   # qualité

# Front-end
cd frontend
npm install
npm run dev                       # http://localhost:5173
npm test                          # tests
npm run build

# Base PostgreSQL locale
docker compose up -d
```

Configuration : copier `.env.example` vers `.env` (jamais commité).

## 6. Conventions de code

### Général
- **Code, noms de variables, commentaires techniques et messages de commit en anglais** ; **interface, messages d'erreur visibles et documentation en français**.
- Petits changements, une préoccupation par Pull Request.
- Pas de code mort, pas de `print` ou `console.log` oubliés, pas de TODO sans identifiant de tâche.

### Back-end (Python / Django)
- PEP 8, formatage Black, lint Ruff.
- **Vues fines**, logique métier dans `services.py`.
- Un serializer par usage (liste, détail, écriture) quand les champs diffèrent.
- Requêtes optimisées : `select_related` et `prefetch_related` pour éviter les requêtes N+1.
- Toute opération qui touche le stock, la commande ou le paiement s'exécute dans `transaction.atomic()`.
- Les migrations sont versionnées et relues ; ne jamais modifier une migration déjà fusionnée.

### Front-end (React)
- Composants fonctionnels et hooks ; composants en PascalCase, hooks en `useXxx`.
- Mobile first (largeur de départ 360 px), Tailwind, composants génériques dans `components/ui/`.
- Appels API uniquement via le client Axios commun (`src/api/`) ; données serveur gérées avec TanStack Query.
- Formulaires : React Hook Form + Zod ; messages d'erreur clairs en français.
- Toujours gérer les états **chargement**, **erreur** et **liste vide**.
- Accessibilité : zones tactiles de 44 px minimum, libellés sur les champs, contrastes suffisants.
- Pas de `localStorage` pour des secrets ; le panier peut être persisté localement.

## 7. Règles d'API

- Préfixe `/api/v1/`, JSON, ressources au pluriel.
- Authentification : `Authorization: Bearer <access_token>` (JWT courte durée + refresh).
- Pagination par défaut (20 éléments), filtres via django-filter.
- Format d'erreur uniforme :

```json
{ "error": { "code": "validation_error", "message": "…", "details": { "field": ["…"] } } }
```

- **Ne crée pas de route absente de `docs/03-architecture.md`** sans la documenter et la signaler.
- Chaque endpoint est documenté (drf-spectacular) et protégé par une permission explicite.

## 8. Règles métier critiques

1. Une **commande concerne un seul vendeur** ; un panier multi-vendeurs crée plusieurs commandes.
2. Le **prix unitaire est copié** dans chaque ligne de commande.
3. Le **stock est décrémenté dans une transaction atomique** à la création de la commande et **restitué** en cas d'annulation ou d'expiration du paiement.
4. Statuts de commande autorisés : `EN_ATTENTE_PAIEMENT`, `CONFIRMEE`, `EN_PREPARATION`, `PRETE`, `LIVREE`, `ANNULEE`. Les transitions suivent le schéma de `docs/03-architecture.md` ; toute autre transition est refusée.
5. **Montants en entiers** (FCFA, sans décimales). Dates en UTC, affichage en heure locale (UTC+1).
6. **Paiements idempotents** : un même webhook ne doit jamais être traité deux fois ; **la signature du webhook est toujours vérifiée**.
7. Un vendeur ne publie qu'une fois **validé** par un administrateur ; il ne voit et ne modifie que **ses** produits et **ses** commandes.
8. Un produit lié à une commande n'est jamais supprimé physiquement (désactivation).
9. Le numéro de téléphone est unique par compte.
10. Les actions d'administration sont écrites dans le **journal d'audit**.

## 9. Sécurité

- **Aucun secret dans le dépôt** (clés API, `SECRET_KEY`, mots de passe) : variables d'environnement uniquement.
- Valider toutes les entrées côté serveur ; ne jamais construire de SQL par concaténation ; échapper les sorties.
- Limitation de débit sur la connexion, l'inscription et le paiement.
- Ne jamais stocker de code secret ni de données de carte.
- Ne jamais journaliser de données personnelles ou de jetons.
- Contrôler le type et la taille des images envoyées.
- Les permissions par rôle et par propriétaire sont **testées**.

## 10. Tests

- Toute fonctionnalité ou correction est livrée **avec ses tests**.
- Back-end : viser au moins **70 %** de couverture sur le code ajouté ; tester les permissions, les cas limites (stock insuffisant, paiement échoué, double webhook) et les transitions de statut.
- Front-end : tester les composants et formulaires critiques.
- Les services externes (paiement, SMS) sont **simulés dans les tests** ; utiliser le bac à sable du prestataire pour les essais manuels.
- Lance les tests et le lint avant de proposer un changement.

## 11. Workflow Git et tâches

- Chaque tâche a un **identifiant** (S1-04, S3-06, etc.) défini dans `docs/05-repartition-des-taches.md`.
- **Chaque membre travaille et pousse uniquement sur sa branche personnelle, qui porte son prénom en minuscules** : `gildas`, `laura`, `stella`, `oumar`, `loana`, `donald`, `eliance`, `hermann` (liste dans `CONTRIBUTING.md`).
- **Règle pour l'assistant IA, avant tout commit ou push** :
  1. Exécute `git branch --show-current`.
  2. Si la branche est `main`, `develop` ou celle d'un autre membre : **arrête-toi, ne commite pas, ne pousse pas**, et demande au développeur de se placer sur sa branche (`git checkout <prénom>`) ou de la créer depuis `develop` (`git checkout develop && git pull && git checkout -b <prénom>`).
  3. Si tu ne sais pas qui est le développeur, **demande son prénom** ; ne devine pas.
  4. Pousse avec `git push origin <prénom>`. Jamais de `git push` vers `main` ou `develop`, jamais de `--force`, jamais de réécriture de l'historique partagé.
  5. Si le développeur ne sait pas faire, **indique-lui les commandes exactes** à taper plutôt que d'agir à sa place.
- Commits : `type(ID-tâche): message court à l'impératif`, avec `feat`, `fix`, `docs`, `refactor`, `test`, `chore` (par exemple `feat(S1-04): ajouter l'API produits`).
- Pull Request de sa branche personnelle vers `develop`, fusion par merge commit (sans squash), branche conservée ; avec le modèle `.github/pull_request_template.md`, relue par un autre membre.
- **Reste dans le périmètre de la tâche** : ne modifie pas le travail d'un autre membre sans en parler (voir les dossiers par rôle dans `docs/taches/`).

## 12. Interdits

- Ne pas ajouter de dépendance sous licence copyleft forte (GPL, AGPL) ni de code copié sans licence : le dépôt est **propriétaire** (voir `LICENSE`) et doit rester privé.
- Ne pas inventer de fonctionnalité, de route, de champ ou de règle métier absents des documents de référence.
- Ne pas contourner la validation, les permissions ou la vérification de signature des webhooks pour « faire passer » un test.
- Ne pas commiter `.env`, des clés, des données réelles d'utilisateurs ou des sauvegardes de base.
- Ne pas ajouter de dépendance lourde, ni de bibliothèque incompatible avec une connexion faible, sans justification.
- Ne pas réécrire ou reformater des fichiers entiers sans rapport avec la tâche.
- Ne pas supprimer de tests pour rendre la CI verte.
- Ne pas affirmer qu'une intégration (Mobile Money, SMS) fonctionne en production sans l'avoir testée en bac à sable.

## 13. Comment travailler avec l'équipe

- **Explique en français**, avec des phrases simples ; le code reste en anglais.
- En cas d'ambiguïté sur un besoin, **pose une seule question précise** ou propose deux options avec leurs conséquences, au lieu de deviner.
- Signale les risques (sécurité, perte de données, impact sur le stock ou les paiements) avant d'agir.
- Résume ce qui a été fait, ce qui reste à faire et comment le tester.
- Si un point des documents semble faux ou dépassé, propose une correction du document en plus du code.

## 14. Definition of Done

Une tâche est terminée lorsque :

- [ ] le code est relu par au moins un autre membre (Pull Request approuvée) ;
- [ ] les tests automatisés passent ;
- [ ] la fonctionnalité a été testée par la QA ;
- [ ] elle est déployée sur l'environnement de test ;
- [ ] elle a été validée par le représentant client ;
- [ ] la documentation concernée (Swagger, `docs/`, README) est à jour.
