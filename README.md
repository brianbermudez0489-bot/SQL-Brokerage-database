# SQL-Brokerage-database
Builds an SQL database that manages the stocks and ETFs of users.

A MySQL 8 database for a small brokerage: clients, accounts, securities, daily prices,
trades and dividends. Designed from scratch (ER model -> 3NF schema), seeded with sample
data, and used to practice queries from basic filtering up to CTEs and window functions.

## Run it
Requires MySQL 8.0+.

```
mysql -u root -p < schema/00_create_database.sql
mysql -u root -p brokerage < schema/01_tables.sql
mysql -u root -p brokerage < seed/<file>.sql
```
Or open the files in MySQL Workbench and run them in order.

This database is the storage layer for the companion Java app,
[JAVA-Stock-Portfolio](https://github.com/brianbermudez0489-bot/JAVA-Stock-Portfolio),
which loads securities, saves trades and runs reports through JDBC.

## Layout
- `schema/` - database and table definitions
- `seed/` - sample data
- `queries/` - query sets, beginner to advanced

## Progress
See [ROADMAP.md](ROADMAP.md).
