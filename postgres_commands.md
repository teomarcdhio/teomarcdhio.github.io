---
layout: default
title: Postgres Commands
parent: Postgres
nav_order: 1
---
### Postgres commands

Connect to a postgres db   
```psql -h <REMOTE HOST> -p <REMOTE PORT> -U <DB_USER> <DB_NAME>```    
Show all databases    
```
\l
```    
Quit psql   
```
\q
```    
Show tables in postgres    
```
\dt
```    
Show schema   
```
\dn
```   
Create db using createdb ( bundled with psql )    
```createdb -h <REMOTE HOST> -p <REMOTE PORT> -U <DB_USER> <DB_NAME>```   
Create db using sql commands   
```psql -h <REMOTE HOST> -p <REMOTE PORT> -U <DB_USER> <DB_NAME> -c 'create database <yournewdb>;'```  
Grant privileges to new db    
```psql -h <REMOTE HOST> -p <REMOTE PORT> -U <DB_USER> <DB_NAME> -c 'grant all privileges on database <yournewdb> to <youruser>;'```      
Create table in postgres    
```
CREATE TABLE accounts (
	user_id serial PRIMARY KEY,
	username VARCHAR ( 50 ) UNIQUE,
	password VARCHAR ( 50 ) ,
	email VARCHAR ( 255 ) UNIQUE 
);
```     
Insert data    
```
INSERT INTO accounts     
(user_id, username, password, email)    
VALUES    
(2, 'John', 'somepassword', 'another@gmail.com');    
```    
Show data in table    
```SELECT * FROM accounts```    
Drop all content of database   
```
DROP SCHEMA public CASCADE;   
CREATE SCHEMA public;    
GRANT ALL ON SCHEMA public TO postgres;   
GRANT ALL ON SCHEMA public TO public;    
```    
Dump db from rmeote server   
```pg_dump -U keycloak -h localhost -p 5432 keycloak > keycloak.sql```    
Restore db to remote server    
```psql -U keycloak -h localhost keycloak < keycloak.sql```    

