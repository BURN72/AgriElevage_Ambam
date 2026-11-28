# 🤝 Guide de contribution

## Branches

| Branche | Usage |
|---------|-------|
| `main` | Version stable (production) |
| `develop` | Intégration des fonctionnalités terminées |
| `<prénom>` | **Branche personnelle** de chaque membre : elle porte son prénom en minuscules (`gildas`, `laura`, `stella`, `oumar`, `loana`, `donald`, `eliance`, `hermann`) |

### Règle de push

- **Chacun pousse uniquement sur sa propre branche**, celle qui porte son nom. Personne ne pousse directement sur `main` ni sur `develop`, ni sur la branche d'un autre membre.
- Le travail arrive dans `develop` uniquement par **Pull Request** depuis sa branche personnelle.
- Pas de `git push --force` (ni `--force-with-lease`) sans l'accord de la Lead Developer.
- L'identifiant de la tâche (`S1-04`, dans votre fichier `docs/taches/`) figure dans le message de commit : `feat(S1-04): ajouter l'API produits`.

| Membre | Branche personnelle |
|--------|---------------------|
| Gildas SEGNING WOUATI | `gildas` |
| Laura NZEMKAM | `laura` |
| Stella SIMO MOKAM | `stella` |
| Oumar ABBA | `oumar` |
| Loana ANGUE | `loana` |
| Donald SOUOP KUATE | `donald` |
| Eliance MENGUE MBIAM | `eliance` |
| Hermann BOUGA NIAMPOU | `hermann` |

Première utilisation :

```bash
git checkout develop && git pull
git checkout -b <votre-prénom>        # une seule fois
git push -u origin <votre-prénom>
```

Au quotidien :

```bash
git checkout <votre-prénom>
git merge develop                     # récupérer le travail des autres
# ... coder, tester ...
git add . && git commit -m "feat(S1-04): ajouter l'API produits"
git push origin <votre-prénom>
```

## Commits

Format : `type(ID-tâche): message court à l'impératif`

| Type | Usage |
|------|-------|
| `feat:` | Nouvelle fonctionnalité |
| `fix:` | Correction |
| `docs:` | Documentation |
| `refactor:` | Réorganisation sans changement de comportement |
| `test:` | Ajout ou modification de tests |
| `chore:` | Configuration, dépendances |

## Pull Request

1. Se placer sur sa branche personnelle et y intégrer `develop` (`git merge develop`).
2. Coder et tester localement, puis pousser sur **sa branche** uniquement.
3. Ouvrir une Pull Request de sa branche vers `develop` avec le modèle fourni.
4. Attendre le résultat de l'intégration continue et la relecture d'**au moins un autre membre** (revue coordonnée par la Lead Developer).
5. Fusionner par **merge commit** (pas de squash, car la branche personnelle est conservée), **ne pas supprimer** la branche, puis refaire `git merge develop` sur sa branche.

## Règles de code

- **Back-end** : PEP 8, Black, Ruff ; logique métier dans `services.py` ; permissions testées.
- **Front-end** : ESLint + Prettier ; composants en PascalCase ; mobile first ; textes en français.
- Code et noms techniques en anglais, interface en français.
- Jamais de secret ou de fichier `.env` dans le dépôt.

## Definition of Done

- [ ] Code relu par au moins un autre membre
- [ ] Tests automatisés au vert
- [ ] Fonctionnalité testée par la QA
- [ ] Déployée sur l'environnement de test
- [ ] Validée par le représentant client
- [ ] Documentation à jour

## Propriété et confidentialité

- Le code appartient au groupe projet (licence propriétaire, voir [LICENSE](LICENSE)) : le dépôt GitHub reste **privé**.
- Ne copiez pas de code d'un autre projet sans en vérifier la licence (pas de code GPL/AGPL ni de code sans licence).
- N'ajoutez que des dépendances à licence compatible avec un code propriétaire (MIT, BSD, Apache 2.0, ISC) ; toute autre licence doit être validée par l'équipe.
- Ne partagez ni le code ni les captures de l'application en dehors du groupe, des enseignants et du jury.

## Travailler avec un assistant IA

Si vous utilisez un agent de code (Cursor, Claude Code, etc.), il lit automatiquement [AGENTS.md](AGENTS.md) ou [.cursorrules](.cursorrules). Relisez toujours le code généré, lancez les tests et vérifiez qu'il respecte les documents de `docs/` avant d'ouvrir une Pull Request.
