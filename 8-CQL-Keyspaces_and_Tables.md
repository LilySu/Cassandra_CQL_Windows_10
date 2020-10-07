#### CREATE KEYSPACE
Outermost container for data, a cluster may contain many key spaces
- a keyspace can have many tables
- a table contains a set of rows of key-value-pair columns
- after the tables, we deal with wide rows consisting of a primary key and a large # of columns
- every row has a primary key specified with data access
- primary key = composite key - made of the partition key, which decides on which nodes our data will be stored and # of clustering columns for sorting data and order stored on disk.

```
CREATE KEYSPACE test_keyspace WITH replication = {'class':'SimpleStrategy','replication_factor':'1'} AND durable_writes = 'true';
```

#### Check Keyspaces
`DESCRIBE KEYSPACES`

#### Use Keyspace
```
USE test_keyspace ;
```

#### CREATE TABLE

```
CREATE TABLE employee_by_id (id int PRIMARY KEY, name text, position text);
```

```
CREATE TABLE employee_by_car_make (car_make text, id int, car_model text, PRIMARY KEY(car_make, id));
```
```
CREATE TABLE employee_by_car_make_sorted (car_make text, age int, id int, name text, PRIMARY KEY(car_make, age, id));
```
```
CREATE TABLE employee_by_car_make_and_model (car_make text, car_model text, id int, name text, PRIMARY KEY((car_make, car_model), id));
```
```
INSERT INTO employee_by_id (id, name, position) VALUES (1, 'John', 'Manager') ;
```
```
DROP TABLE employee_bar_car_make ;
```
```
DESCRIBE TABLES;
```