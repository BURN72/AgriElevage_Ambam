# Back-end : API Django REST

Structure prévue (voir `docs/03-architecture.md`) :

```
backend/
├── config/settings/     # base.py, dev.py, prod.py, test.py
├── apps/
│   ├── accounts/  catalog/  orders/  payments/  deliveries/
│   └── reviews/  notifications/  dashboard/  moderation/  common/
├── requirements.txt
└── requirements-dev.txt
```

Chaque application contient : `models.py`, `serializers.py`, `views.py`, `urls.py`, `services.py`, `permissions.py` (si besoin) et un dossier `tests/`.

## Démarrage (après l'initialisation du Sprint 0, tâche S0-11)

```bash
python -m venv venv
source venv/bin/activate        # Windows : venv\Scripts\activate
pip install -r requirements-dev.txt
cp ../.env.example ../.env      # puis renseigner les variables
python manage.py migrate
python manage.py runserver
```

API : `http://localhost:8000/api/v1/` · Swagger : `http://localhost:8000/api/docs/`

Les dépendances de `requirements.txt` sont un point de départ : les versions sont à confirmer et à figer lors de l'initialisation.
