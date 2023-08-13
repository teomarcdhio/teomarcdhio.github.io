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
```\d```    
Quit psql   
```\q```    
Show tables in postgres    
```\dt```    
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
