#### Connect to Postgres
```bash
$ sudo -u postgres psql
psql (10.5 (Ubuntu 10.5-1.pgdg16.04+1))                                                               
Type "help" for help.                                                       

```

#### Create new User
```sql
CREATE ROLE your_username with CREATEDB LOGIN encrypted password 'your_password';
```

#### Create database with new user
```sql
CREATE DATABASE your_db_name WITH owner 'your_username' encoding 'utf8';
```

#### Connect to the database with new user
```bash
$ psql -h localhost -U your_username -d your_db_name
Password for user your_username:
psql (10.5 (Ubuntu 10.5-1.pgdg16.04+1))
SSL connection (protocol: TLSv1.2, cipher: ECDHE-RSA-AES256-GCM-SHA384, bits: 256, compression: off)
Type "help" for help.

your_db_name=> 
```

