# POSTRESQL

## Common commands

```
psql -U postgres: connect to the CLI with the user "postgres", will require password used during installation

\l: list databases

\du: show users

\conninfo: show currently selected database

\c <database>: switch to another database

\d: show available tables in the currently selected database

\d <table>: shows table structure

\q: exit interface

SELECT * FROM table_name;: performs a sql, semicolon is required at the end
```