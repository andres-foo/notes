# MYSQL


## BASIC
```sql
--- read
SELECT name, description 
FROM products
WHERE status = 1;

--- insert
INSERT INTO products (sku, name, description, price)
VALUES ('ABC1234', 'Phonetastic', 'A phone', 12345);

--- update
UPDATE products 
SET name = 'Phone', description = 'An amazing phone'
WHERE id = 10;

--- delete
DELETE FROM products WHERE id = 10;
```

## LIKE

```sql
--- two characters before "A"
SELECT * FROM products WHERE code LIKE '__A';

--- any number of characters before "A"
SELECT * FROM products WHERE code LIKE '%A';
```

## NESTED
TODO: create a better example
```sql
/*
Consider... 
*/ 
SELECT *
FROM products 
WHERE products.status IN (
    SELECT *
    FROM status
    WHERE active = 1
);
```