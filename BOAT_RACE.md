# Superset for Boat Race

## Preparation

```
echo "sqlalchemy-bigquery" >> ./docker/requirements-local.txt
```

## Run

```
docker compose -f docker-compose-non-dev.yml up
```

## Backup

バックアップを取る。

```
docker compose exec superset superset export_datasources -f /app/superset_home/(date +"%Y-%m-%d-%H-%M-%S")_dataset.zip
docker compose exec superset export_dashboards -f /app/superset_home/(date +"%Y-%m-%d-%H-%M-%S")_dashboards.zip
```

バックアップを復元する。

```
docker compose exec superset import_datasources -p <path / filename>
docker compose exec superset import_dashboards -p <path / filename>
```
