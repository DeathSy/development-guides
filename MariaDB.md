# Basic MariaDB Configuration 

### Step 1 - First time installed

For new MariaDB installations, the next step is to run the included security script. This script changes some of the less secure default options for things like remote root logins and sample users.

Run the security script:

```
$ sudo mysql_secure_installation
```

This will take you through a series of prompts where you can make some changes to your MariaDB installation’s security options. The first prompt will ask you to enter the current database root password. Since you have not set one up yet, press ENTER to indicate “none”.

```
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
```

The next prompt asks you whether you’d like to set up a database root password. On Ubuntu, the root account for MariaDB is tied closely to automated system maintenance, so we should not change the configured authentication methods for that account. Doing so would make it possible for a package update to break the database system by removing access to the administrative account. Type N and then press <code>ENTER</code>

```
. . .
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] N
```

From there, you can press Y and then ENTER to accept the defaults for all the subsequent questions. This will remove some anonymous users and the test database, disable remote root logins, and load these new rules so that MariaDB immediately implements the changes you have made.

### Step 2 - Creating an administrative user that employs password authentication

We will create a new account called admin with the same capabilities as the root account, but configured for password authentication. Open up the MariaDB prompt from your terminal:

```
$ sudo mariadb
```

Then create a new user with root privileges and password-based access. Be sure to change the username and password to match your preferences:

```
MariaDB[(none)]> GRANT ALL ON *.* TO 'admin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
```

(Optional) If you want to only grant user previleges to a specific database use the following command:

```
MariaDB[(none)]> GRANT ALL ON 'your_databas_name'.* TO 'admin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
```

Flush the privileges to ensure that they are saved and available in the current session:

```
MariaDB [(none)]> FLUSH PRIVILEGES;
```

### Setp 3 - Start/Stop/Restart MariaDB server

To Start/Stop/Restart MariaDB server run the following command:

##### macOS
```
$ brew services start mariadb
$ brew services stop mariadb
$ brew services restart mariadb
```

##### Windows
```
$ sudo systemctl start mariadb
$ sudo systemctl stop mariadb
$ sudo systemctl restart mariadb
```
