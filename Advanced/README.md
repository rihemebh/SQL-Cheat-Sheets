
# Nested Queries 

## With Select
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

 - **OPERATOR**
   - EXISTS / NOT EXISTS
   - BETWEEN 
   - IN 
   

# Views 
### Creation
#### Virtual View 
- ``CREATE VIEW view_name(col1,col2,..) AS  query  [WITH CHECK OPTION] [WITH READ ONLY] ``
- `` REPLACE VIEW view_name(cols) AS query  [WITH CHECK OPTION] [WITH READ ONLY]``
#### Concrete View 
- ``CREATE CONCRETE VIEW view_name(col1,col2,..) AS  query  [WITH CHECK OPTION] [WITH READ ONLY] ``
 
### Delete
- `` DROP VIEW view_name ``

