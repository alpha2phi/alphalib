# Welcome to alphalib
> A library for your daily data engineering and data science routines.


This file will become your README and also the index of your documentation.

## Install

```bash
pip install alphalib
```

## How to use

### Ingest from Excel to `accounts` table in PostgreSQL

```python
# Ingest from Excel to `accounts` table in PostgreSQL
excel_source = file_sources.get(FileSource.Excel, file_path="data/accounts.xlsx")
config = {
    'host': 'localhost',
    'port': 5432,
    'db': 'testdb',
    'user': 'user1',
    'password': 'userpwd'
}
pgsql_target = db_targets.get(DatabaseTarget.PostgreSQL, **config)
ingest(excel_source, pgsql_target, 'accounts')
```

    2020-12-12 21:26:59,943 INFO(): {'user_id': INTEGER(), 'username': VARCHAR(length=50), 'password': VARCHAR(length=50), 'email': VARCHAR(length=255), 'created_on': TIMESTAMP(), 'last_login': TIMESTAMP()}


    
    Total records in data/accounts.xlsx - 100
    user_id - 100
    username - 100
    password - 100
    email - 100
    created_on - 1
    last_login - 1


### Ingest from CSV to `accounts` table in MySQL

```python
# Ingest from CSV to `accounts` table in MySQL
csv_source = file_sources.get(FileSource.CSV, file_path="data/accounts.csv")
config = {
    'host': 'localhost',
    'port': 3306,
    'db': 'testdb',
    'user': 'user1',
    'password': 'userpwd'
}
mysql_target = db_targets.get(DatabaseTarget.MySQL, **config)
ingest(csv_source, mysql_target, 'accounts')
```

    2020-12-12 21:35:29,017 INFO(): {'user_id': INTEGER(), 'username': VARCHAR(length=50), 'password': VARCHAR(length=50), 'email': VARCHAR(length=255), 'created_on': TIMESTAMP(), 'last_login': TIMESTAMP()}


    
    Total records in data/accounts.csv - 100
    user_id - 100
    username - 100
    password - 100
    email - 100
    created_on - 1
    last_login - 1

