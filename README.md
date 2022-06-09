# appache-ignite1
Exercice 1 
Ce fichier présente les codes utilisés pour chaque question

Q1 : 

  site 1
  
C:\apache-ignite-slim-2.13.0-bin\bin>ssh root@207.180.211.231 
   
   ./ignite.sh ../examples/config/example-ignite.xml
  
  site 2
  
C:\apache-ignite-slim-2.13.0-bin\bin>ssh root@149.102.155.141
 
 ./ignite.sh ../examples/config/example-ignite.xml


Q2 : 

 ./sqlline.sh -u jdbc:ignite:thin://149.102.155.141/
 
 CREATE TABLE City (id LONG PRIMARY KEY, name VARCHAR) WITH "template=replicated";

INSERT INTO City (id, name) VALUES (1, 'Porto Novo');

INSERT INTO City (id, name) VALUES (2, 'Come');

INSERT INTO City (id, name) VALUES (3, 'Ouidah');

SELECT * FROM City;


Q3 :
SELECT * FROM City;


Q4 :
./ignite.sh ../examples/config/example-ignite.xml

./sqlline.sh -u jdbc:ignite:thin://207.180.211.231/

SELECT * FROM City;


Q5 :
CREATE TABLE Person (id LONG, name VARCHAR, city_id LONG, PRIMARY KEY (id, city_id)) WITH "backups=1, affinityKey=city_id";

INSERT INTO Person (id, name, city_id) VALUES (1, 'John Koffi', 3);

INSERT INTO Person (id, name, city_id) VALUES (2, 'Jane GBOBA', 2);

INSERT INTO Person (id, name, city_id) VALUES (3, 'Mary AFFI', 1);

INSERT INTO Person (id, name, city_id) VALUES (4, 'Richard TOGODO', 2);

SELECT * FROM PERSON;

Q6: 

SELECT * FROM PERSON;


