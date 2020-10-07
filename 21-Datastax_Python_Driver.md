#### Create Table
```
CREATE TABLE python_test (id uuid PRIMARY KEY, first_name text, last_name text) ;
```

Run cassandratest.py

```
SELECT * FROM python_test;
```
```
 id                                   | first_name | last_name
--------------------------------------+------------+-----------
 196f8ec4-030e-4da3-9e29-f6cdd4ad3970 |        bob |      hope
```