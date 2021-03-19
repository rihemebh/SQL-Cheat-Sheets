# SQL-Cheat-Sheet *Basics*

## Managing Users
  - ``GRANT privileges ON table TO user (PUBLIC) [WITH GRANT OPTION ]``
  - ``REVOKE privileges ON table FROM user``
- Privileges: 
    - `` ALL PREVILEGES``
    - ``UPDATE (columns)``
    - ``SELECT (columns)``
    - ``INSERT (columns)``
    - ``DELETE (columns)``
    - ``ALTER (columns)``
    - `` INDEX``
###  ROLES : 
- ``
    CREATE ROLE role_name; 
``
- `` 
   GRANT previlege ON table TO role; 
``
- ``  
 GRANT role TO user; 
``

## Managing Tables

### Creation 
  - CREATE TABLE table_name ( 
                  
      column_name  [TYPE] [COLUMN_CONSTRAINT]  ,
      [TABLE_CONSTRAINT]

      );
      
      - **COLUMN CONSTRAINT**: 
      [CONSTRAINT constraint_name]
         -  AUTO_INCREMENT
         -  UNIQUE
         -  NULL / NOT NULL 
         -  DEFAULT 'val'
         -  PRIMARY KEY
         -  REFRENCES 'table_name'
         -  CHECK 'constraint'
        
      - **TABLE CONSTRAINT** :
        - CONSTRAINT const_name CONST_TYPE (Column1, column2,... )
        - FOREIGN KEY(column_name) REFERENCES table_name [FOREIGN KEY CONSTRAINT]
        
      - **FOREIGN KEY CONSTRAINT**: 
        - ON DELETE {CASCADE/SET NULL/ SET DEFAULT}
        - ON UPDATE {CASCADE/SET NULL/ SET DEFAULT}   
              
      - **TYPE**: 
        - VARCHAR(n)
        - INTEGER 
        - BOOL 
        - DATE
        - DATETIME
     
  ##### FIND MORE: `https://www.w3schools.com/sql/sql_datatypes.asp`
       
                  
### Modification
- ``ALTER TABLE table_name [OPERATION];``

 
    - OPERATIONS :
      - `` RENAME TO`` new_table_name
      - ``RENAME COLUMN`` column_name TO new_name
      - ``DROP COLUMN`` column_name
      - ``DROP CONSTRAINT`` const_name
      - ``ADD COLUMN`` column_name
      - ``ADD CONSTRAINT`` constraint_details
      - ``MODIFY COLUMN`` column_name
      

### Delete 
    DROP TABLE Table_name {CASCADE CONSTRAINT | RESTRICT };
## Managing Data
### SELECT 
### UPDATE
### INSERT
### DELETE

###
