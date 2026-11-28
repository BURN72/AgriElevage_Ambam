# 🌾 AgriElevage Ambam

> Plateforme web de vente directe de produits agricoles et d'élevage, qui relie producteurs, éleveurs et acheteurs à Ambam (Cameroun).

![Statut](https://img.shields.io/badge/statut-en%20d%C3%A9veloppement-orange)
![Licence](https://img.shields.io/badge/licence-propri%C3%A9taire-red)
![M%C3%A9thode](https://img.shields.io/badge/m%C3%A9thode-Scrum-blue)

> « AgriElevage Ambam » est le nom de travail du projet.

---

## 🎯 Le projet

Les petits producteurs et éleveurs d'Ambam subissent des prix imposés par les intermédiaires, des pertes après récolte et un accès limité aux acheteurs. **AgriElevage Ambam** leur permet de publier leurs produits, de gérer leur stock et de vendre directement, avec paiement Mobile Money, depuis un smartphone et même avec une connexion faible.

**ODD visé en priorité** : ODD 2 (Faim « zéro »), avec des contributions aux ODD 1, 8, 9 et 12.

## 📚 Documentation

| Document | Contenu |
|----------|---------|
| [Cahier des charges](docs/01-cahier-des-charges.md) | Contexte, objectifs, périmètre, personas, contraintes, risques, recette |
| [Stack technologique](docs/02-stack-technologique.md) | Technologies retenues et justification |
| [Architecture](docs/03-architecture.md) | Architecture, modèle de données, API, sécurité, déploiement |
| [Requirements](docs/04-requirements.md) | Exigences fonctionnelles et non fonctionnelles |
| [Répartition des tâches](docs/05-repartition-des-taches.md) | Tâches par sprint pour toute l'équipe |
| [Tâches individuelles](docs/taches/README.md) | Un fichier par membre (front-end et back-end) |
| [Registre des décisions](docs/06-registre-des-decisions.md) | Choix validés, sources et points restant à confirmer |
| [Concurrents vérifiés](docs/07-etude-de-marche.md) | Concurrents au Cameroun et différenciation |
| [Guide de contribution](CONTRIBUTING.md) | Branche personnelle par membre, commits, Pull Requests, Definition of Done |
| [AGENTS.md](AGENTS.md) et [.cursorrules](.cursorrules) | Instructions pour les agents IA (Cursor, Claude Code, etc.) |

## ✨ Fonctionnalités

- Comptes avec rôles (acheteur, vendeur, administrateur)
- Catalogue avec photos, recherche et filtres
- Panier, commande, suivi de commande
- Paiement Mobile Money et paiement à la livraison
- Retrait ou livraison avec frais par zone
- Notifications (dans l'application et SMS ; lien WhatsApp de contact)
- Tableau de bord vendeur
- Administration et modération
- Avis sur les vendeurs
- Application installable (PWA), mode hors ligne de base

## 🏗️ Technologies

| Couche | Technologie |
|--------|-------------|
| Front-end | React 19, Vite 8, Tailwind CSS 4, TanStack Query |
| Back-end | Django 5.2 LTS, Django REST Framework, JWT |
| Base de données | PostgreSQL |
| Paiement | CamPay (MTN MoMo et Orange Money) |
| SMS | API SMS Cameroun d'Orange |
| Images | Cloudinary (offre gratuite) |
| CI/CD | GitHub Actions |
| Hébergement | Cloudflare Pages (front), Render (API), Neon (PostgreSQL) |

## 📁 Structure du dépôt

```
AgriElevage_Ambam/
├── backend/        # API Django REST (apps : accounts, catalog, orders, payments, ...)
├── frontend/       # Application React (PWA)
├── docs/           # Documentation, maquettes, tests, recettes, tâches
├── .github/        # CI et modèle de Pull Request
├── .env.example
├── docker-compose.yml
├── AGENTS.md       # instructions pour les agents IA
├── .cursorrules    # règles pour Cursor
└── CONTRIBUTING.md
```

## 🚀 Démarrage

> Le code est initialisé au Sprint 0 (tâche S0-11). Les commandes ci-dessous s'appliquent ensuite.

```bash
git clone https://github.com/BURN72/AgriElevage_Ambam.git
cd AgriElevage_Ambam
cp .env.example .env            # renseigner les variables
docker compose up -d            # base PostgreSQL locale (optionnel)
```

- Back-end : voir [backend/README.md](backend/README.md)
- Front-end : voir [frontend/README.md](frontend/README.md)

## 🧭 Méthode et équipe

Projet réalisé en **Scrum** dans le cadre du cours GSI 712. Le Product Owner est l'enseignant.

| Rôle | Membre |
|------|--------|
| Product Owner | M. METILI Donatien |
| Scrum Master | SEGNING WOUATI Gildas |
| Lead Developer (back-end) | NZEMKAM F. Laura S. |
| Back-end | SIMO MOKAM Stella |
| Front-end | ABBA Oumar |
| Front-end, UX/UI | ANGUE Loana |
| Représentant client | SOUOP KUATE Donald |
| QA-testeurs | MENGUE MBIAM Eliance, BOUGA NIAMPOU Hermann |

## 🗺️ Feuille de route

| Phase | Objectif | Statut |
|-------|----------|--------|
| Sprint 0 | Backlog, étude de marché, maquettes, architecture, environnement | 🔄 |
| Sprint 1 | Comptes et catalogue | ⏳ |
| Sprint 2 | Tableau de bord, administration et tests | ⏳ |
| Sprint 3 | Commande et paiement | ⏳ |
| Pilote | Test avec des producteurs et acheteurs à Ambam | ⏳ |

## 📄 Licence

**Licence propriétaire : tous droits réservés au groupe projet** (voir [LICENSE](LICENSE)). Le dépôt doit rester **privé** ; aucune copie, modification ou diffusion sans autorisation écrite du groupe. Les bibliothèques tierces conservent leurs propres licences.

---

<p align="center">Fait avec ❤️ à Ambam, Cameroun 🇨🇲</p>
