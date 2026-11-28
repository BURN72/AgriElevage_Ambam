# 🧰 Stack technologique

Ce document présente les technologies retenues pour AgriElevage Ambam. Les versions ont été **vérifiées en novembre 2026** (installation de l'ensemble des dépendances, contrôle de compatibilité, build de démonstration). Les justifications détaillées, les alternatives écartées et les sources sont dans [06-registre-des-decisions.md](06-registre-des-decisions.md).

> Règle : les versions sont figées par les fichiers de verrouillage (`package-lock.json` côté front, `requirements.txt` à versions bornées côté back). Toute montée de version majeure est décidée en équipe.

---

## 1. Vue synthétique

| Couche | Technologie | Version retenue |
|--------|-------------|-----------------|
| Front-end | React + Vite | React 19, Vite 8 |
| Routage | React Router | 7 |
| Style | Tailwind CSS (plugin Vite) | 4 |
| Back-end | Django (LTS) + Django REST Framework | Django 5.2 LTS, DRF 3.18 |
| Base de données | PostgreSQL | 16 (local), Neon (hébergé) |
| Authentification | JWT (djangorestframework-simplejwt) | 5.5 |
| Documentation API | drf-spectacular (OpenAPI/Swagger) | 0.28 ou plus |
| Paiement Mobile Money | CamPay (MTN MoMo et Orange Money) | API REST |
| SMS | API « SMS Cameroun » d'Orange (tous opérateurs) | API REST |
| Images | Cloudinary (offre gratuite) | SDK Python 1.44 ou plus |
| Tests back-end | pytest, pytest-django, factory_boy, coverage | pytest 9 |
| Tests front-end | Vitest, Testing Library | Vitest 5 |
| CI/CD | GitHub Actions | |
| Hébergement | Cloudflare Pages (front), Render (API), Neon (base) | offres gratuites |
| Python / Node.js | Python 3.12 ou plus, Node.js 22.12 ou plus (22 LTS ou 24/26 LTS) | |

---

## 2. Front-end

| Besoin | Choix | Justification |
|--------|-------|---------------|
| Framework | **React 19** | Maîtrisé par l'équipe, large écosystème |
| Outil de build | **Vite 8** (+ `@vitejs/plugin-react`) | Démarrage rapide, build léger |
| Routage | **React Router 7** (`react-router-dom`) | Routes protégées par rôle |
| Appels API et cache | **Axios** + **TanStack Query 5** | Chargement, erreurs, cache |
| Formulaires | **React Hook Form** + **Zod 4** + `@hookform/resolvers` | Validation simple et fiable |
| Style | **Tailwind CSS 4** via `@tailwindcss/vite` | Mobile first ; pas de PostCSS ni d'autoprefixer à configurer |
| Graphiques | **Recharts 3** | Tableau de bord vendeur |
| PWA | **vite-plugin-pwa 2** | Manifeste, service worker, cache hors ligne |
| État global | Contexte React + TanStack Query ; panier dans le stockage local | Suffisant, évite une dépendance |
| Tests | **Vitest 5** + **Testing Library** + **jsdom** | Intégrés à Vite |
| Qualité | **ESLint 10** + **Prettier 3** | Style uniforme |

**Principes** : mobile first (360 px), composants réutilisables, structure par fonctionnalité (`features/`), textes en français, images servies avec transformation automatique (format et qualité) pour économiser la connexion.

Configuration Vite de référence (validée par un build) :

```js
// frontend/vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'
import { VitePWA } from 'vite-plugin-pwa'

export default defineConfig({
  plugins: [
    react(),
    tailwindcss(),
    VitePWA({ registerType: 'autoUpdate', manifest: { name: 'AgriElevage Ambam', short_name: 'AgriElevage' } }),
  ],
  test: { environment: 'jsdom' },
})
```

Avec Tailwind 4, le fichier CSS principal contient simplement `@import "tailwindcss";`.

---

## 3. Back-end

| Besoin | Choix | Justification |
|--------|-------|---------------|
| Langage | **Python 3.12 ou plus** | Compétence de l'équipe |
| Framework | **Django 5.2 LTS** + **Django REST Framework** | Version à support long ; admin intégré, ORM, sécurité par défaut. Django 6.x n'est pas retenu (support court) |
| Authentification | **SimpleJWT** | Jeton d'accès court + jeton de rafraîchissement |
| Filtres | **django-filter** | Recherche et filtres du catalogue |
| Documentation | **drf-spectacular** | Schéma OpenAPI et Swagger UI |
| CORS | **django-cors-headers** | Autoriser le front-end |
| Configuration | **python-decouple**, **dj-database-url** | Variables d'environnement |
| Images | **Pillow** (validation), **cloudinary** (envoi) | Contrôle puis stockage externe |
| Appels HTTP | **requests** | CamPay, API SMS |
| Fichiers statiques | **WhiteNoise** | Service simple en production |
| Serveur | **Gunicorn** | Serveur WSGI |
| Base | **PostgreSQL** (pilote `psycopg` 3) | Transactions fiables (stock, paiement) |
| Tests | **pytest**, **pytest-django**, **factory_boy**, **coverage** | Tests unitaires et d'intégration |
| Qualité | **Ruff** + **Black** | Lint et format |

**Principes** : API REST versionnée (`/api/v1/`), transactions atomiques pour stock, commandes et paiements, vues fines et logique dans `services.py`, permissions par rôle.

Compatibilité vérifiée : Django 5.2, DRF, SimpleJWT, django-filter, django-cors-headers et drf-spectacular s'installent ensemble sans conflit, `manage.py check` et la génération du schéma OpenAPI passent.

---

## 4. Services externes (choix validés)

### 4.1 Paiement Mobile Money : CamPay

- Agrégateur local acceptant **MTN et Orange Mobile Money** via une API unique.
- **Bac à sable** disponible (site de démonstration avec numéros de test pour les cas « réussi » et « échoué », par opérateur) : le développement et les tests n'ont besoin d'aucun vrai paiement.
- Montants en **entiers** (pas de décimales), numéros au format `237XXXXXXXXX` : cohérent avec la règle ED-02.
- Fonctions de collecte (encaissement) et de retrait (reversement).

**Règles d'intégration** (indépendantes du fournisseur) :

1. Chaque commande envoie à CamPay une **référence externe** (identifiant de la commande).
2. À la réception d'un webhook, le serveur **n'accorde pas confiance au contenu** : il rappelle l'API du prestataire pour **vérifier le statut réel** de la transaction, puis met à jour le paiement (traitement idempotent).
3. Le jeton d'accès CamPay est conservé côté serveur uniquement.
4. Le passage en production exige la validation du compte marchand par le prestataire : la demande est lancée au Sprint 0.

**Repli** : paiement à la livraison (déjà prévu) ; un second prestataire (par exemple Smobilpay/E-nkap) reste possible grâce à une interface `PaymentProvider` unique dans `apps/payments/`.

### 4.2 SMS : API « SMS Cameroun » d'Orange

- Envoi vers **tous les opérateurs** (MTN, Orange, Nexttel), paquets de SMS achetés avec une SIM Orange.
- **Nom d'expéditeur** à faire valider : environ 5 jours ouvrés (15 pour MTN) ; des retards de remise vers MTN sont signalés par le fournisseur : la demande est lancée dès le Sprint 0.
- **Usage limité aux événements clés** pour maîtriser le coût : nouvelle commande (vendeur), commande confirmée et commande prête (acheteur), code de réinitialisation du mot de passe.
- Interface `SmsDriver` (`log` en développement, `orange` en production, autre fournisseur possible).
- **WhatsApp** : pas d'API WhatsApp Business dans le MVP ; un bouton « Contacter par WhatsApp » (lien `wa.me`) est ajouté sur la fiche vendeur et la commande.

### 4.3 Images : Cloudinary (offre gratuite)

- **25 crédits par mois**, sans carte bancaire ; 1 crédit = 1 000 transformations, 1 Go de stockage ou 1 Go de bande passante, au choix.
- Dimensionnement du pilote : environ 30 produits × 5 photos de 300 Ko, soit moins de 0,1 Go : très largement dans l'offre.
- Le disque du serveur Render gratuit est **éphémère** : aucune image ne doit y être stockée.
- Flux : le serveur contrôle l'image (type, taille maximale 5 Mo, 5 photos par produit), l'envoie à Cloudinary et enregistre l'identifiant public ; le front affiche des URL transformées (largeur adaptée, format et qualité automatiques).

---

## 5. Hébergement et environnements (choix validés)

| Rôle | Service | Offre | Points d'attention |
|------|---------|-------|--------------------|
| Front-end | **Cloudflare Pages** | Gratuite : bande passante et requêtes illimitées, 500 builds par mois, domaines personnalisés | Un seul build à la fois |
| API Django | **Render** (Web Service) | Gratuite : 750 h par mois | Mise en veille après 15 min sans trafic, réveil d'environ 1 minute ; système de fichiers éphémère |
| Base PostgreSQL | **Neon** | Gratuite, **sans expiration** : 1 Go par projet, mise à l'arrêt après 5 min d'inactivité | Plafond de 1 Go ; quota de calcul mensuel |

**Écartés** :
- **Vercel Hobby** : réservé à un usage personnel **non commercial** par ses conditions ; la plateforme prévoit de la vente et une commission.
- **PostgreSQL gratuit de Render** : **expire au bout de 30 jours** (suppression après 14 jours de grâce) : inacceptable.

**Impact sur le pilote** : le premier chargement après une période d'inactivité peut prendre environ une minute. Mesures : message de chargement explicite dans l'interface, cache PWA du catalogue, informer les participants du pilote ; si nécessaire, passage de l'API sur une offre payante d'entrée de gamme (tarif à consulter chez le prestataire).

| Environnement | Usage | Front | Back | Base |
|---------------|-------|-------|------|------|
| **Local** | Développement | `npm run dev` (5173) | `runserver` (8000) | PostgreSQL via Docker |
| **Test** | Recette et tests QA | Cloudflare Pages (branche `develop`) | Render (service de test) | Neon (branche ou projet de test) |
| **Production** | Pilote | Cloudflare Pages (branche `main`) | Render | Neon (projet de production) |

**Sauvegardes** : Neon permet de créer des branches et de restaurer ; en plus, un export `pg_dump` planifié (hebdomadaire pendant le pilote) est stocké hors de la plateforme.

---

## 6. Outils de l'équipe

| Usage | Outil |
|-------|-------|
| Versionnement | Git + GitHub (**dépôt privé**) |
| Gestion de projet | Tableau Kanban (GitHub Projects) |
| Maquettes | Figma (ou équivalent) |
| Test d'API | Postman ou Insomnia, Swagger UI |
| Communication | Groupe WhatsApp, réunions Scrum |
| Documentation | Markdown dans `docs/` |
| Intégration continue | GitHub Actions (tests et lint à chaque Pull Request) |

---

## 7. Prérequis de développement

| Outil | Version |
|-------|---------|
| Python | 3.12 ou plus |
| Node.js | 22.12 ou plus (LTS) |
| PostgreSQL | 16 (ou Docker avec `docker-compose.yml`) |
| Git | récent |

---

## 8. Licences des dépendances

Le dépôt étant **propriétaire** ([LICENSE](../LICENSE)), seules des dépendances à licence permissive sont admises (MIT, BSD, Apache 2.0, ISC, ou équivalentes). Les bibliothèques retenues relèvent de ces familles ; `psycopg` est sous LGPL, ce qui autorise son usage comme dépendance non modifiée. Un contrôle automatique des licences (`pip-licenses`, `license-checker`) est ajouté à l'intégration continue au Sprint 2.

---

## 9. Conventions

| Sujet | Convention |
|-------|------------|
| Python | PEP 8, Black, Ruff |
| JavaScript | ESLint + Prettier, composants en PascalCase, hooks en `useXxx` |
| Nommage | Code en anglais, textes visibles en français |
| API | Ressources au pluriel, JSON, codes HTTP standards, erreurs au format uniforme |
| Git | Branches `main`, `develop` et une branche personnelle par membre (son prénom en minuscules, seule branche sur laquelle il pousse) ; commits `type(ID-tâche): message` |
| Revue | Toute Pull Request est relue par un autre membre (revue coordonnée par la Lead Developer) |

Voir aussi [CONTRIBUTING.md](../CONTRIBUTING.md).
