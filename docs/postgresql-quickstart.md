# PostgreSQL Quickstart

Install PostgreSQL, create your first database, and take a backup you can restore. Commands are shown for Ubuntu; package names differ slightly on other systems.

## Install
```bash
sudo apt update
sudo apt install postgresql
sudo systemctl enable --now postgresql
```

## Create a database and user
```bash
sudo -u postgres psql
```
```sql
CREATE USER appuser WITH PASSWORD 'change-me';
CREATE DATABASE appdb OWNER appuser;
GRANT ALL PRIVILEGES ON DATABASE appdb TO appuser;
```

## Connect and verify
```bash
psql -h localhost -U appuser -d appdb -c '\l'
```
You should see `appdb` in the database list.

## Back up and restore
```bash
pg_dump -h localhost -U appuser appdb > appdb-backup.sql
psql -h localhost -U appuser -d appdb < appdb-backup.sql
```

**Warning:** A backup you have never restored is a hope, not a backup. Test restores on a schedule.
