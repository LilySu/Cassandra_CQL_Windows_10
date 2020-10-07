
#### Insert Data into Table
```
INSERT INTO employee_by_id (id, name, position) VALUES (2, 'Bob', 'CEO') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('BMW', 1, 'Sports Car') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('AUDI', 2, 'Truck') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('AUDI', 5, 'Hatchback') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('BMW', 4, 'Sports Car') ;
```

#### Select from Table
```
SELECT * FROM employee_by_car_make WHERE car_make='BMW' ORDER BY id;
```
 car_make | id | car_model
----------+----+------------
      BMX |  1 | Sports Car


#### Insert Data into Table
```
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('BMW','HATCHBACK', 1, 'John') ;
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('AUDI', 'Truck', 8, 'FRANK') ;
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('BMX', 'Truck', 7, 'AMY') ;
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('AUDI', 'Sports Car', 4, 'TIM') ;
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('AUDI', 'Sports Car', 5, 'JIM') ;
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id, name) VALUES ('AUDI', 'Sports Car', 6, 'NICK') ;
```

#### Insert Data into Table
```
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('AUDI', 8, 'Sports Car') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('MERC', 3, 'Saloon') ;
INSERT INTO employee_by_car_make (car_make, id, car_model) VALUES ('MERC', 6, 'Saloon') ;
```


#### This Will Mean name Header value will be Null
```
INSERT INTO employee_by_car_make_and_model (car_make, car_model, id) VALUES ('BMW', 'HATCHBACK', 3) ;
```

#### Select Filter
```
SELECT * FROM employee_by_car_make_and_model WHERE car_make= 'BMW' AND car_model='HATCHBACK' ;
```
 car_make | car_model | id | name
----------+-----------+----+------
      BMW | HATCHBACK |  1 |  Bob
      BMW | HATCHBACK |  2 | null
      BMW | HATCHBACK |  3 | null

