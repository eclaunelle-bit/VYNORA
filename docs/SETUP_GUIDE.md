# 🚀 Setup Guide - Vynora

## Installation du Backend

### Prérequis
- Python 3.9+
- PostgreSQL 12+
- pip & virtualenv

### Étapes

1. **Créer un environnement virtuel**
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

2. **Installer les dépendances**
```bash
pip install -r requirements.txt
```

3. **Configurer les variables d'environnement**
```bash
cp .env.example .env
# Éditer .env avec vos configurations
```

4. **Démarrer le serveur**
```bash
python -m uvicorn app.main:app --reload
```

Le serveur sera accessible à `http://localhost:8000`

## Installation du Mobile

### Prérequis
- Flutter SDK
- Android Studio ou Xcode

### Étapes

1. **Installer les dépendances**
```bash
cd mobile
flutter pub get
```

2. **Lancer l'application**
```bash
flutter run
```

## Installation avec Docker

```bash
docker-compose up -d
```

Cela va démarrer:
- PostgreSQL sur le port 5432
- FastAPI Backend sur le port 8000
- Redis sur le port 6379
