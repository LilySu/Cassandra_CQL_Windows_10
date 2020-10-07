```
SELECT * FROM employee_by_car_make ;
```
```
 car_make | id | car_model
----------+----+------------
      BMX |  1 | Sports Car
      BMX |  4 | Sports Car
     MERC |  3 |     Saloon
     MERC |  6 |     Saloon
     AUDI |  2 |      Truck
     AUDI |  5 |  Hatchback
     AUDI |  8 | Sports Car
```

#### Writetime - Find Out When Item Inserted into Table
```
SELECT car_make, car_model, writetime(car_model) FROM employee_by_car_make ;
```
```
 car_make | car_model  | writetime(car_model)
----------+------------+----------------------
      BMX | Sports Car |     1602018053307000
      BMX | Sports Car |     1602018411020000
     MERC |     Saloon |     1602019109699000
     MERC |     Saloon |     1602019120387000
     AUDI |      Truck |     1602018096459000
     AUDI |  Hatchback |     1602018119356000
     AUDI | Sports Car |     1602019087500000
```

#### Change or Update Value from Table
```
UPDATE employee_by_car_make USING TTL 60 SET car_model='TRUCK' WHERE car_make='BMW' AND id=2 ;
```

#### Add a Column
```
SELECT * FROM employee_by_id ;
```
```
 id | name | position
----+------+----------
  1 | John |  Manager
  2 |  Bob |      CEO
```
```
ALTER TABLE employee_by_id ADD phone set<text>;
```
```
SELECT * FROM employee_by_id ;
```
```
 id | name | phone | position
----+------+-------+----------
  1 | John |  null |  Manager
  2 |  Bob |  null |      CEO
```

#### Updating Altering Existing Values in Table Using Variables
```
UPDATE employee_by_id SET phone = {'343','565'} WHERE id =1 ;
```
```
SELECT * FROM employee_by_id ;
```
```
 id | name | phone          | position
----+------+----------------+----------
  1 | John | {'343', '565'} |  Manager
  2 |  Bob |           null |      CEO
```

#### Adding Variables
```
UPDATE employee_by_id SET phone = phone + {'555'} WHERE id =1 ;
```
```
SELECT * FROM employee_by_id ;
```
```
 id | name | phone                 | position
----+------+-----------------------+----------
  1 | John | {'343', '555', '565'} |  Manager
  2 |  Bob |                  null |      CEO
```

#### Subtracting Variables
```
UPDATE employee_by_id SET phone = phone - {'565'} WHERE id =1 ;
```
#### ORDER BY is Only Supported on the Clustered Columns of Primary Key
#### ALLOW FILTERING Bypasses this but this may be unperformant as data may be access through a large # of tables in multiple cluster
```
SELECT * FROM employee_by_id WHERE name='John' ALLOW FILTERING ;
```
```
 id | name | phone          | position
----+------+----------------+----------
  1 | John | {'343', '555'} |  Manager
```

#### Create Index
```
CREATE INDEX ON employee_by_id (name);
```
```
SELECT * FROM employee_by_id WHERE name='John' ;
```
```
 id | name | phone          | position
----+------+----------------+----------
  1 | John | {'343', '555'} |  Manager
```

