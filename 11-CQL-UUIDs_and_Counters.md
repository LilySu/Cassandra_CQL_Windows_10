#### Create Table with Uuid Type
```
CREATE TABLE employee_by_uuid (id uuid PRIMARY KEY, first_name text, last_name text) ;
```
#### Insert to Autogenerate Uuid
```
INSERT INTO employee_by_uuid (id, first_name, last_name) VALUES (uuid(), 'tom', 'dunne');
INSERT INTO employee_by_uuid (id, first_name, last_name) VALUES (uuid(), 'som', 'dunne');
INSERT INTO employee_by_uuid (id, first_name, last_name) VALUES (uuid(), 'tim', 'smith');
INSERT INTO employee_by_uuid (id, first_name, last_name) VALUES (uuid(), 'bob', 'hanson');
```
```
SELECT * FROM employee_by_uuid
```
```
 id                                   | first_name | last_name
--------------------------------------+------------+-----------
 e5ee566e-9963-4682-b181-95e701f1f7c8 |        bob |    hanson
 daf6b263-cc61-4881-9919-b9b121ed912b |        tom |     dunne
 2f51f0d1-e72d-45cd-b349-78f6f1f3e042 |        tim |     smith
 87ea1615-adea-404f-9841-c8bef20b78b0 |        tom |     dunne
```

#### Timeuuid
```
CREATE TABLE employee_by_timeuuid (id timeuuid PRIMARY KEY, first_name text, last_name text);
```

#### Insert
```
INSERT INTO employee_by_timeuuid (id, first_name, last_name) VALUES (now(), 'tim', 'jones') ;
INSERT INTO employee_by_timeuuid (id, first_name, last_name) VALUES (now(), 'ally', 'smith') ;
INSERT INTO employee_by_timeuuid (id, first_name, last_name) VALUES (now(), 'kate', 'smith') ;
```
#### Working with Counters
```
CREATE TABLE purchases_by_customer_id (id uuid PRIMARY KEY, purchase counter) ;
```

#### Update
```
UPDATE purchases_by_customer_id SET purchase = purchase + 1 WHERE id=uuid();
UPDATE purchases_by_customer_id SET purchase = purchase + 1 WHERE id=uuid();
UPDATE purchases_by_customer_id SET purchase = purchase + 1 WHERE id=uuid();
```
```
SELECT * FROM purchases_by_customer_id ;
```
```
 id                                   | purchase
--------------------------------------+----------
 10698d7e-87fc-49da-8ed8-dca9734daf77 |        1
 63047cb2-a17e-47d6-89f0-27e5418443df |        1
 4bf6ff97-b44d-4fad-8053-cd4ae277c985 |        1
```

#### Add 1 to Counter via Update
```
UPDATE purchases_by_customer_id SET purchase = purchase + 1 WHERE id=4bf6ff97-b44d-4fad-8053-cd4ae277c985;
```
```
SELECT * FROM purchases_by_customer_id ;
```
```
 id                                   | purchase
--------------------------------------+----------
 10698d7e-87fc-49da-8ed8-dca9734daf77 |        1
 63047cb2-a17e-47d6-89f0-27e5418443df |        1
 4bf6ff97-b44d-4fad-8053-cd4ae277c985 |        2
```