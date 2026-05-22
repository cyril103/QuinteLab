# QuintéLab

Site statique de pronostic hippique fictif par la data.

## Contenu

- `index.html` : application statique principale.
- `site_data.json` : données générées pour alimenter le site.
- `docker-compose.yml` : service nginx local pour servir le site.

## Lancer en local avec Docker Compose

```bash
docker compose up -d
```

Puis ouvrir : <http://localhost:8781>

## Mise à jour des données

Le site est généré depuis les scripts du projet Quinté fictif, puis publié ici sous forme de fichiers statiques.

Publication automatique actuelle : `/opt/data/scripts/quintelab_publish.sh` régénère le site depuis l’état live, commit les changements et pousse `main` vers GitHub. Le cron Hermes `quintelab-site-publish` l’exécute toutes les 30 minutes. Le Docker Compose local sert directement ce même dossier sur `site-test-nginx` sans copie intermédiaire.
