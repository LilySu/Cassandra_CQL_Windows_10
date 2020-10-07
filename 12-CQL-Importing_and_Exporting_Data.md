#### Create Empy Table
```
CREATE TABLE test_csv_import (car_make text, car_model text, start_year int, id int, first_name text, last_name text, department text, PRIMARY KEY(car_make, car_model, start_year, id));
```

#### Upload Existing .csv File
```
COPY test_csv_import (car_make, car_model, start_year, id, first_name, last_name, department) FROM 'C:\Users\lilyx\Desktop\cassandra\cassandra.csv' WITH DELIMITER=',' AND HEADER=TRUE;
```
```
SELECT * FROM test_csv_import ;
```
```
 car_make | car_model | start_year | id | department | first_name | last_name
----------+-----------+------------+----+------------+------------+-----------
      BMW |   Compact |       2012 |  9 |         IT |     Georgy |      Depp
      BMW |   Compact |       2019 |  5 |         IT |      Angel |      Depp
      BMW |    Saloon |       2011 |  1 |         IT |     Johnny |      Depp
      BMW |    Saloon |       2011 | 11 |         IT |    Natalie |      Depp
      BMW |    Saloon |       2013 |  7 |         IT |      Julia |      Depp
    LEXUS |    Saloon |       2015 |  3 |         IT |       Brad |      Depp
   NISSAN |    Saloon |       2021 |  6 |         HR |       Matt |    Streep
     AUDI |   Compact |       2017 |  4 |         HR |        Tom |    Streep
     AUDI |    Saloon |       2012 | 10 |         FI |     Dwayne |    Streep
     AUDI |    Saloon |       2013 |  2 |         HR |      Meryl |    Streep
     AUDI |    Saloon |       2013 |  8 |         HR |     Nicole |    Streep
```

#### Save Out Entire Table as a .csv to the Local Directory
```
COPY test_csv_import TO 'C:\Users\lilyx\Desktop\cassandra\cassandra-from-cqlsh.csv' WITH DELIMITER=',';
```

#### Save Out Specific Headers
```
COPY test_csv_import (car_mark, department, first_name) TO 'C:\Users\lilyx\Desktop\cassandra\cassandra-specified-columns.csv' WITH DELIMITER=',';
```
