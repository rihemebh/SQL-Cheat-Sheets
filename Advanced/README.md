
# Nested Queries 

|  With Select  | With Update | With Insert | With Delete |
| --- | --- | --- | --- |
| ``SELECT (SELECT query that returns one value) FROM table  WHERE conditions``  <br />  <br /> ``SELECT columns FROM (SELECT query that retuns multiple rows ) WHERE condition``  <br />  <br />  `` SELECT column_name FROM   tables  WHERE  column_name OPERATOR  (SELECT Query)`` | ``UPDATE table SET column_name = new_value WHERE OPERATOR (SELECT Query)``| ``INSERT INTO table_name [ (columns..) ]  VALUES (SELECT Query that reurns one value , [val , ...])``  | ``DELETE FROM TABLE_NAME WHERE OPERATOR (SELECT Query)`` |
<!--## With Select
       SELECT ( SELECT Query that returns one value 
      // Don't forget to make the join condition with the table called in the main select )
       FROM table 
       WHERE conditions 
  ------------------------------    
       SELECT columns 
       FROM (SELECT query that retuns multiple values )
       WHERE condition
---------------------------------------
      SELECT column_name
      FROM   tables 
      WHERE  column_name OPERATOR  (SELECT Query)
## With Update 
       UPDATE table
      SET column_name = new_value
      WHERE OPERATOR [ VALUE ] (SELECT Query)
## With Insert 
       INSERT INTO table_name [ (columns..) ] 
       VALUES (SELECT Query that reurns one value , [val , ...]) 
   ## With Delete
       DELETE FROM TABLE_NAME
       WHERE OPERATOR (SELECT Query)
-->
 **OPERATOR**  : EXISTS / NOT EXISTS  -- BETWEEN -- IN 
   

# Views 
### Creation
#### Virtual View 
- ``CREATE VIEW view_name(col1,col2,..) AS  query  [WITH CHECK OPTION] [WITH READ ONLY] ``
- `` REPLACE VIEW view_name(cols) AS query  [WITH CHECK OPTION] [WITH READ ONLY]``
#### Concrete View 
- ``CREATE CONCRETE VIEW view_name(col1,col2,..) AS  query  [WITH CHECK OPTION] [WITH READ ONLY] ``
 
### Delete
- `` DROP VIEW view_name ``
# Recursive Queries (^SQL3)

     WITH [RECURSIVE] name AS (
     Initialisation Query 
     UNION ALL
     Recursive Query with terminate condition in where 
     )
     SELECT * from name; -- Displaying result data 
     
     
- PostgreSQL requires the RECURSIVE keyword in recursive definitions but it is optional for other databases.

<img height=300 src='https://cdn.sqlservertutorial.net/wp-content/uploads/SQL-Server-Recursive-CTE-execution-flow.png' >

# PL/SQL 
    DECLARE
       VarName [constant] type [:= val];
    BEGIN

    EXCEPTION
      
    END
    
- TYPES
    - INTEGER , VARCHAR(n) , CHAR ,DATE , DECIMAL ... 
    - TABLES , LINE ..
    - %TYPE  %ROWTYPE
     
# Functions and Procedures 
## Functions 
       CREATE FUNCTION func_name[(in | out | in out parms)] RETURN returnType AS 
       DECLARE
       VarName [constant] type [:= val];
       
       BEGIN
       -- SELECT must always be used with INTO
          
       RETURN statement
       
       EXCEPTION
       WHEN excp
       THEN RETURN NULL;
       END func_name;
       
  ## Procedures
       CREATE procedure proc_name[(in | out | in out parms)] AS 
       DECLARE
       VarName [constant] type [:= val];
       
       BEGIN
         
       EXCEPTION
       WHEN excp
       THEN RETURN NULL;
       END proc_name;

# Triggers

       CREATE TRIGGER trigger_name
       {BEFORE | AFTER} {INSERT | UPDATE| DELETE } [OF colums]
       ON table_name
       [REFERENCING {OLD | NEW | PARENT } [ROW] [AS] alias]
       [FOR EACH ROW]
          
        --trigger_body (pl/sql bloc) or calling a function or procedure ;

# Cursor
 - It helps you store multiple lines and Mange access to them

        CURSOR cursorname IS SELECT ..FROM .. WHERE..
        FOR UPDATE|DELETE [OF listeColonnes ]][NOWAIT WAIT durée]
        
# Exceptions

we add exceptions within a PL/SQL bloc : 

       DECLARE 
       -- Variables, curseurs, exceptions définies par l'utilisateur
       BEGIN *

       -- Instructions 

       EXCEPTION (facultatif)
       -- Actions à effectuer lorsque des erreurs se produisent
       END; *
  -------------------------------------       
         
      EXCEPTION 
      WHEN DefinedException | costum exception THEN
      statement;
      ...
   
      WHEN OTHERS THEN
      statement;
      
  - Defined exception
      - NO_DATA_FOUND 
      - TOO_MANY_ROWS
      - ..
 - Costum exception 
      - **Declaration** : exception_name EXCEPTION; 
      - **Raising an exception** : RAISE  exception_name;
 
