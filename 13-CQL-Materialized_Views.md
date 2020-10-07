
```
SELECT * FROM test_keyspace.employee_by_department ;
```
```
 department | car_make | car_model | id | start_year | first_name | last_name
------------+----------+-----------+----+------------+------------+-----------
         HR |     AUDI |   Compact |  4 |       2017 |        Tom |    Streep
         HR |     AUDI |    Saloon |  2 |       2013 |      Meryl |    Streep
         HR |     AUDI |    Saloon |  8 |       2013 |     Nicole |    Streep
         HR |   NISSAN |    Saloon |  6 |       2021 |       Matt |    Streep
         IT |      BMW |   Compact |  5 |       2019 |      Angel |      Depp
         IT |      BMW |   Compact |  9 |       2012 |     Georgy |      Depp
         IT |      BMW |    Saloon |  1 |       2011 |     Johnny |      Depp
         IT |      BMW |    Saloon |  7 |       2013 |      Julia |      Depp
         IT |      BMW |    Saloon | 11 |       2011 |    Natalie |      Depp
         IT |    LEXUS |    Saloon |  3 |       2015 |       Brad |      Depp
         FI |     AUDI |    Saloon | 10 |       2012 |     Dwayne |    Streep
```

#### Set Materialized Views

```
CREATE MATERIALIZED VIEW test_keyspace.employee_by_department
                 ... AS SELECT *
                 ... FROM test_keyspace.test_csv_import
                 ... WHERE department IS NOT NULL AND
                 ... car_make IS NOT NULL AND
                 ... car_model IS NOT NULL AND
                 ... id IS NOT NULL
                 ... AND start_year IS NOT NULL
                 ... PRIMARY KEY (department, car_make, car_model, id, start_year);
```

#### Test Our Materialized Views
```
SELECT * FROM test_keyspace.employee_by_department WHERE department='IT';
```
```

 department | car_make | car_model | id | start_year | first_name | last_name
------------+----------+-----------+----+------------+------------+-----------
         IT |      BMW |   Compact |  5 |       2019 |      Angel |      Depp
         IT |      BMW |   Compact |  9 |       2012 |     Georgy |      Depp
         IT |      BMW |    Saloon |  1 |       2011 |     Johnny |      Depp
         IT |      BMW |    Saloon |  7 |       2013 |      Julia |      Depp
         IT |      BMW |    Saloon | 11 |       2011 |    Natalie |      Depp
         IT |    LEXUS |    Saloon |  3 |       2015 |       Brad |      Depp
```
```
SELECT * FROM test_keyspace.employee_by_car_make WHERE car_make='BMW';
```
```
 car_make | id | car_model
----------+----+-----------
      BMW |  1 |     TRUCK
```
