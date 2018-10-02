Create a new user on MySQL and grant priviliges

Try this to create the user:

```
CREATE USER 'user'@'hostname';
```

Try this to give it access to the database dbTest:

```
GRANT ALL PRIVILEGES ON dbTest.* To 'user'@'hostname' IDENTIFIED BY 'password';
```

replace dbTest with the database you want to give access to and user with the name of the user you want to give access to.

If you are running the code/site accessing MySQL on the same machine, hostname would be localhost.

Now, the break down.

GRANT - This is the command used to create users and grant rights to databases, tables, etc.

ALL PRIVILEGES - This tells it the user will have all standard privileges. This does not include the privilege to use the GRANT command however.

dbtest.* - This instructions MySQL to apply these rights for use in the entire dbtest database. You can replace the * with specific table names or store routines if you wish.

TO 'user'@'hostname' - 'user' is the username of the user account you are creating. Note: You must have the single quotes in there. 'hostname' tells MySQL what hosts the user can connect from. If you only want it from the same machine, use localhost

IDENTIFIED BY 'password' - As you would have guessed, this sets the password for that user.

------------------------------------------------------------------------