# MYSQL

## CREATE DATABASE
```sql
CREATE DATABASE my_app;
```

## CREATE TABLE
```sql
-- asd
CREATE TABLE [IF NOT EXISTS] status (
    status_id INT NOT NULL,
    description VARCHAR(30) NOT NULL,
    PRIMARY KEY (status_id)
);

CREATE TABLE [IF NOT EXISTS] users (
    user_id INT NOT NULL AUTO_INCREMENT,
    username VARCHAR(30),
    email VARCHAR(50),
    status_id INT DEFAULT 1,
    PRIMARY KEY (user_id),    
    FOREIGN KEY (status_id) REFERENCES status(status_id)
);
```

## BASIC CRUD
```sql
-- insert
INSERT INTO users (username, email) 
VALUES ('jsmith', 'jsmith@example.com');

-- read
SELECT username, email 
FROM clients
WHERE status_id = 1;

-- update
UPDATE users 
SET email = 'jsmith2023@example.com', status_id = 2
WHERE user_id = 1;

-- delete
DELETE FROM users WHERE user_id = 10;
```
## DISTINCT

```sql
-- only select different country values
SELECT DISTINCT country FROM clients;

-- number of different countries in the clients table
SELECT count(DISTINCT country) FROM clients;
```
## LIKE WILDCARDS

```sql
-- "_" means exactly one character
-- matches A-A34, A-223, etc
SELECT * FROM products WHERE sku_code LIKE 'A-___';

-- "%" means zero or more characters
-- matches anything ending in .com
SELECT * FROM users WHERE email LIKE '%.com';
```

## NESTED

```sql
/*
** Consider a table with all possible statuses for a user, among
** those statuses you have: "permanently banned" and 
** "temporarily banned". The following nested query will get all
** users who are not banned.
*/ 
SELECT * FROM users 
WHERE users.status_id IN (
    SELECT status.status_id
    FROM status
    WHERE status.description NOT LIKE "%banned%"
);
```