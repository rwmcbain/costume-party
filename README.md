# costume-party

my SQL commands
we create a db for every project and a specific user in the db for that project
this is for security purposes!

'''
create database costume_party;
create user 'ru55ell'@'localhost' identified by 'pooty';
grant all privileges on costume_party.* to 'ru55ell'@'localhost';
'''