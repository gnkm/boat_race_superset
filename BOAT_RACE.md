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

コンテナに入る。

```
docker compose exec superset bash
```

バックアップを取る。

```
superset export_datasources
superset export_dashboards
```

バックアップを復元する。

```
superset import_datasources -p <path / filename>
superset import_dashboards -p <path / filename>
```
