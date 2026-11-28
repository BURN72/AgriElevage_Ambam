# 📒 Registre des décisions

Ce registre ferme les « points d'ombre » du projet. Chaque décision indique son **motif**, ses **alternatives écartées** et le **statut** : ✅ validé (vérifié sur les sources officielles en novembre 2026) ou ⚠️ à confirmer hors de l'équipe (démarche externe ou avis juridique). Les sources sont les sites officiels des services concernés, à consulter de nouveau avant le pilote car les offres changent.

## 1. Décisions techniques

| N° | Sujet | Décision | Motif et alternatives | Statut |
|----|-------|----------|-----------------------|--------|
| D-01 | Version Django | **5.2 LTS** | Support à long terme ; Django 6.x a un support court | ✅ |
| D-02 | Versions front | React 19, Vite 8, Tailwind 4, Router 7, Zod 4, Recharts 3, Vitest 5, vite-plugin-pwa 2 | Installation complète testée sans conflit, build de démonstration réussi | ✅ |
| D-03 | Python / Node | Python 3.12+, Node 22.12+ (CI en Node 22) | Exigence de Vite 8 ; Node 22 est une version LTS | ✅ |
| D-04 | Langue du code | Code en anglais, interface et documents en français | Convention déjà fixée dans AGENTS.md | ✅ |
| D-05 | Durée des sprints | **2 semaines** | Compatible avec le calendrier académique ; ajustable à la rétrospective | ✅ |

## 2. Services externes

| N° | Sujet | Décision | Motif et alternatives | Statut |
|----|-------|----------|-----------------------|--------|
| D-06 | Paiement | **CamPay** (MTN MoMo et Orange Money) | Bac à sable avec numéros de test, API simple, montants entiers. Repli : paiement à la livraison ; interface `PaymentProvider` pour changer de prestataire | ✅ choix ; ⚠️ validation du compte de production et frais réels à confirmer auprès de CamPay |
| D-07 | Webhook paiement | Le serveur revérifie le statut auprès de l'API avant de valider | Ne jamais se fier au contenu reçu ; traitement idempotent | ✅ |
| D-08 | Commission | **0 % pendant le pilote** | Évite la question réglementaire des agrégateurs de paiement | ⚠️ tout modèle de commission après le pilote exige un avis juridique |
| D-09 | SMS | **API SMS Cameroun d'Orange**, SMS limités aux événements clés | Couvre tous les opérateurs ; coût maîtrisé. Nom d'expéditeur : environ 5 jours ouvrés (Orange) à 15 (MTN) | ✅ choix ; ⚠️ approbation du nom d'expéditeur |
| D-10 | WhatsApp | Simple lien `wa.me` ; pas d'API WhatsApp Business | Aucun coût, aucune validation | ✅ |
| D-11 | Front-end | **Cloudflare Pages** | Offre gratuite sans limite de bande passante. Vercel Hobby écarté : usage non commercial uniquement | ✅ |
| D-12 | API | **Render** (service web gratuit) | Mise en veille après 15 min, réveil d'environ 1 min, disque éphémère : à signaler au pilote | ✅ avec limites connues |
| D-13 | Base de données | **Neon** (PostgreSQL gratuit, 1 Go, sans expiration) | La base gratuite de Render expire après 30 jours : écartée | ✅ |
| D-14 | Images | **Cloudinary** (offre gratuite, 25 crédits par mois), envoi via le back-end | Disque Render éphémère inutilisable ; besoin du pilote très inférieur au quota | ✅ |
| D-15 | Sauvegarde | Export `pg_dump` hebdomadaire hors plateforme | Les offres gratuites ne garantissent pas la restauration | ✅ |

## 3. Juridique et conformité

| N° | Sujet | Décision | Statut |
|----|-------|----------|--------|
| D-16 | Données personnelles | Appliquer la **loi n° 2024/017** (en vigueur depuis le 23 juin 2026) : consentement explicite et révocable à l'inscription, collecte minimale, accès et suppression des données, journalisation | ✅ intégré aux exigences |
| D-17 | Commerce électronique | Appliquer la **loi n° 2010/021** : informations du vendeur, prix, conditions générales, mentions légales | ✅ intégré aux exigences |
| D-18 | Hébergement hors du Cameroun | Les données sont hébergées à l'étranger (Render, Neon, Cloudflare, Cloudinary) | ⚠️ **à confirmer** : la loi encadre les transferts de données hors du pays ; l'autorisation ou la déclaration auprès de l'autorité compétente et les textes d'application restent à vérifier avant d'ouvrir à de vrais utilisateurs |
| D-19 | Propriété intellectuelle | **Licence propriétaire : tous droits réservés au groupe projet** ; dépôt privé ; dépendances à licence permissive uniquement | ✅ choix du groupe ; texte de la licence rédigé par le groupe ; il réserve les droits de l'établissement et fait primer ses règles en cas de conflit. ⚠️ Les règles exactes de l'ESTLC restent à connaître (à demander à l'enseignant)  |
| D-20 | Nom du projet | « AgriElevage Ambam » est un nom de travail | ⚠️ vérifier la disponibilité avant tout usage public |

## 4. Points restant à traiter hors de l'équipe

1. Autorisation ou déclaration pour l'hébergement de données personnelles à l'étranger (D-18).
2. Compte de production CamPay : validation et frais (D-06).
3. Nom d'expéditeur SMS : délai d'approbation (D-09).
4. Règles de l'établissement sur la propriété du projet (D-19).
5. Avis juridique avant toute commission sur les ventes (D-08).

Ces points sont suivis dans les tâches S0-06 (risques) et S0-08 (services externes).

## 5. Sources consultées

- Documentation et conditions des services : Render (offre gratuite), Neon (tarifs), Cloudflare Pages (limites), Cloudinary (tarifs), Vercel (conditions Hobby), CamPay (documentation et bac à sable), Orange Developer (API SMS Cameroun).
- Registres officiels des paquets : npm et PyPI (versions et compatibilités).
- Textes : loi n° 2024/017 relative à la protection des données personnelles ; loi n° 2010/021 régissant le commerce électronique au Cameroun.
