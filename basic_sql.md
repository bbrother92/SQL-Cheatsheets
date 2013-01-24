#Basic SQL
##Show
Show databases `SHOW DATABASES`

Change database `USE <db_name>`

Show tables `SHOW TABLES`

Show table columns `EXPLAIN <table_name>`

##Select
Select all `SELECT * FROM <table_name>`

Select alias for table `SELECT <column_name> FROM <table_name> AS <alias_name>`

Select alias for column `SELECT <column_name> AS <alias_name> FROM <table_name>`

Select top `SELECT TOP <number>` or `<number> PERCENT` `* FROM <table>`

Select only different values `SELECT DISTINCT <column_name(s)> FROM <table_name>`

[advanced select][]
###Where clause

	SELECT <column_name(s)> FROM <table_name>
	WHERE <column_name> <operator> <value>
Text values need quotes `'Example text value'`, numeric values don't `12`.
<table>
  <tr>
    <th>Operator</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>=</code></td>
    <td>Equal</td>
  </tr>
  <tr>
    <td><code><></code> or <code>!=</code></td>
    <td>Not equal</td>
  </tr>
  <tr>
    <td><code>></code></td>
    <td>Greater than</td>
  </tr>
  <tr>
    <td><code><</code></td>
    <td>Less than</td>
  </tr>
  <tr>
    <td><code>>=</code></td>
    <td>Greater than or equal</td>
  </tr>
  <tr>
    <td><code><=</code></td>
    <td>Less than or equal</td>
  </tr>
  <tr>
    <td><code>BETWEEN</code></td>
    <td>Between an inclusive range</td>
  </tr>
  <tr>
    <td><code>LIKE</code></td>
    <td>Search for a pattern</td>
  </tr>
  <tr>
    <td><code>IN</code></td>
    <td>To specify multiple possible values for a column</td>
  </tr>
  <tr>
    <td><code>IS NULL</code></td>
    <td>Select NULL values</td>
  </tr>
  <tr>
    <td><code>IS NOT NULL</code></td>
    <td>Don't select NULL values</td>
  </tr>  
</table>
**The LIKE operator** `WHERE <column_name> LIKE <pattern>`<br>
<table>
  <tr>
    <th>Wildcard</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td><code>%</code></td>
    <td>Substitute for zero or more characters</td>
    <td><code>LIKE '%e%'</code>. Find everything that contains an 'e'</td>
  </tr>
  <tr>
    <td><code>_</code></td>
    <td>Substitute for exactly one character</td>
    <td><code>LIKE '_e'</code>. Find everything that has 2 character and the last letter is an 'e'</td>
  </tr>
  <tr>
    <td><code>[charlist]</code></td>
    <td>Any single character in charlist</td>
    <td><code>LIKE '[abc]%'</code>. Find everything starts with an 'a', 'b' or 'c'</td>
  </tr>
  <tr>
    <td><code>[^charlist]</code> or <code>[!charlist]</code></td>
    <td>Any single character not in charlist</td>
    <td><code>LIKE '[abc]%'</code>. Find everything does not start with an 'a', 'b' or 'c'</td>
  </tr>
</table>
**The IN operator** `WHERE <column_name> IN (<value>)`

**The BETWEEN operator** `WHERE <column_name> BETWEEN <value> AND <value>`
###And & Or operators
Operators used to filter records based on more than one condition.

	SELECT <column_name(s)> FROM <table_name>
	WHERE <column_name> <operator> <value>
		
		AND <column_name> <operator> <value> //this value must be true
		OR <column_name> <operator> <value> //this or the other value is true
###Order by

	SELECT <column_name(s)> FROM <table_name>
	ORDER BY <column_name> ASC | DESC

##Create
###Create database

	CREATE DATABASE <db_name>
###Create table

	CREATE TABLE <table_name> (
		<column_name> <data_type>,
		<column_name> <data_type>
	)
	
	//set default value for column and set not null (constraints)
		<column_name> <data_type> default <default_value>,
		<column_name> <data_type> NOT NULL default <default_value>
	
	//set primary key and auto increment
		<column_name> <data_type> NOT NULL IDENTITY PRIMARY KEY
more on [data types][] and more on [constraints][]
###Alter table

	ALTER TABLE <table_name> 
		RENAME <new_table_name>
		ADD <column_name> <data_type> //etc..
		DROP <column_name>
		ALTER COLUMN <column_name> <new_data_type>
		//change name in mssql using sp_rename <table_name>, <new_table_name>
###Create index
Indexes allow the database application to find data fast. But updating a table with indexes takes more time, because the indexes also need an update. Only index on columns (and tables) that will be frequently searched against.

	CREATE INDEX <index_name> ON <table_name> (<column_name(s)>)
	
	CREATE UNIQUE INDEX <index_name> ON <table_name> (<column_name(s)>)

A `UNIQUE` index does not allow duplicate values. When creating an index for multiple columns separate them by a `,`.
##Insert

	INSERT INTO <table_name>(<column_1>, <column_3>)
					  VALUES(<value_column_1>, <value_column_3>)

##Update

	UPDATE <table_name>
	SET <column_name1> = <value>, <column_name2> = <value>, …
	WHERE <column_name> <operator> <value>

##Delete/Drop
###Delete row

	DELETE FROM <table_name> WHERE <column_name> <operator> <value>
###Delete data from table

	TRUNCATE TABLE <table_name>
###Drop table

	DROP TABLE <table_name>
###Drop index

	DROP INDEX <table_name>.<index_name>




[data types]: data_types.md
[constraints]: constraints.md
[advanced select]: advanced_select.md