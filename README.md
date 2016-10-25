 costume-party

## 3. My SQL Commands
we create a db for every project and a specific user in the db for that project
this is for security purposes!

'''
create database costume_party;
create user 'ru55ell'@'localhost' identified by 'pooty';
grant all privileges on costume_party.* to 'ru55ell'@'localhost';
'''

## 2. Environment Variables
Our environment variables are stored in .env but may also be declared as needed.

'''
DB_USER=ru55ell
DB_PWD=pooty
DB_NAME=costume_party
DB_TYPE=mysql
DB_SERVER=localhost
'''

## 3. Database Connection
A database connection is defined inside of db.js. It contains all code needed to 
connet to mysql

'''
//	./models/db.js

'use strict';


// loads environments variables from .env
require('dotenv').config();

// knex is a database adapter for node
// npm install knex && npm install lodash
// lodash is a dependency of knex
var db = require('knex')({
	client: process.env.DB_TYPE,
	connection: {
		host: process.env.DB_SERVER,
		user: process.env.DB_USER,
		password: process.env.DB_PWD,
		database: process.env.DB_NAME
	}
});

module.exports = db;
'''