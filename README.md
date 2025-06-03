# WordPress Static Pipeline

Ce projet permet de générer automatiquement une version statique d'un site WordPress et de la déployer sur Cloudflare Pages via GitHub Actions.

## Prérequis

- Docker et Docker Compose
- Un compte GitHub
- Un compte Cloudflare
- Un site WordPress fonctionnel

## Configuration

1. Démarrer l'environnement WordPress :
```bash
docker-compose up -d
```

2. Accéder à WordPress sur http://localhost:8080 et installer le plugin WP2Static

3. Configurer les secrets GitHub suivants :
- `CLOUDFLARE_ACCOUNT_ID`: ID de votre compte Cloudflare
- `CLOUDFLARE_API_TOKEN`: Token API Cloudflare avec les permissions Pages:Write

## Structure

- `.github/workflows/`: Contient les workflows GitHub Actions
- `static/`: Dossier contenant le site statique généré
- `compose.yaml`: Configuration Docker pour WordPress

## Workflow

1. Les modifications sont poussées sur la branche main
2. GitHub Actions génère le site statique avec WP2Static
3. Le site statique est déployé sur Cloudflare Pages