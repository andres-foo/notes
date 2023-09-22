# MYSQL

## CREATE DATABASE

```sql
CREATE DATABASE my_app;
```

## CREATE TABLE

```sql
-- will require the ids to be created and passed in the insert
CREATE TABLE [IF NOT EXISTS] status (
    status_id INT NOT NULL,
    description VARCHAR(30) NOT NULL,
    PRIMARY KEY (status_id)
);

-- won't need to define the id and status in the insert
CREATE TABLE [IF NOT EXISTS] clients (
    client_id INT NOT NULL AUTO_INCREMENT,
    username VARCHAR(30),
    email VARCHAR(50),
    status_id INT DEFAULT 1,
    PRIMARY KEY (client_id),
    FOREIGN KEY (status_id) REFERENCES status(status_id)
);
```

## BASIC CRUD

```sql
-- insert
INSERT INTO clients (username, email)
VALUES ('jsmith', 'jsmith@example.com');

-- read
SELECT username, email
FROM clients
WHERE status_id = 1;

-- update
UPDATE clients
SET email = 'jsmith2023@example.com', status_id = 2
WHERE user_id = 1;

-- delete
DELETE FROM clients WHERE user_id = 10;
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
SELECT * FROM clients
WHERE clients.status_id IN (
    SELECT status.status_id
    FROM status
    WHERE status.description NOT LIKE "%banned%"
);
```

## ON DELETE

```sql
-- When a client is deleted, all payments for that client will be deleted as well
CREATE TABLE payment (
    payment_id INT NOT NULL AUTO_INCREMENT,
    amount INT NOT NULL,
    client_id INT NOT NULL,
    PRIMARY KEY (payment_id),
    FOREIGN KEY (client_id) REFERENCES clients(client_id)
    ON DELETE CASCADE
);


-- When a client is deleted, all payments for that client will have the client_id set to NULL
CREATE TABLE payment (
    payment_id INT NOT NULL AUTO_INCREMENT,
    amount INT NOT NULL,
    client_id INT,
    PRIMARY KEY (payment_id),
    FOREIGN KEY (client_id) REFERENCES clients(client_id)
    ON DELETE SET NULL
);

```

## INDEXES

Indexes speed up queries for frequently used columns:

```sql
-- create an index
CREATE INDEX idx_lastname
ON clients (lastname);

-- remove an index
ALTER TABLE clients
DROP INDEX idx_lastname;
```

To see if an index is used in a query use the keyword `EXPLAIN`:

```sql
-- if the index is being used, it will appear under "key"
EXPLAIN SELECT * FROM clients WHERE lastname = 'Smith';

-- if the index is not used, the column "key" will be empty
-- indexes are not good for "LIKE" statements with a wildcard in the beginning
EXPLAIN SELECT * FROM clients WHERE lastname LIKE '%mit%';
```

## FULL TEXT SEARCH

```sql
-- Set keys for columns in creation
CREATE TABLE posts (
    post_id INT NOT NULL AUTO_INCREMENT,
    title VARCHAR(30),
    body TEXT,
    PRIMARY KEY (post_id),
    FULLTEXT KEY (title, body)
);

-- or alter an existing table
ALTER TABLE post
ADD FULLTEXT(title, body);

-- now do a query
-- it will give priority to posts that contain both terms
SELECT * FROM post WHERE
    MATCH (title, body)
    AGAINST('android phone');
```
