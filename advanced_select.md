#Advanced select
##Joins
`SELECT <column_name(s)> FROM <table_name>` + the join syntax
<table>
  <tr>
    <th>Syntax</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>INNER JOIN table2 ON<br> table1.column = table2.column</code></td>
    <td>Returns rows when there is at least one match in both tables</td>
  </tr>
  <tr>
    <td><code>LEFT JOIN table2 ON<br> table1.column = table2.column</code></td>
    <td>Returns all rows from the left table (table1), even if the are no matches in the right (table2)</td>
  </tr>
  <tr>
    <td><code>RIGHT JOIN table2 ON<br> table1.column = table2.column</code></td>
    <td>Returns all rows from the right table (table2), even if the are no matches in the left (table1)</td>
  </tr>
  <tr>
    <td><code>FULL JOIN table2 ON<br> table1.column = table2.column</code></td>
    <td>Return rows where there is a match in one of the tables</td>
  </tr>
</table>

##Union
The `UNION` Operator combines two or more `SELECT` statements.

	SELECT <column_name(s)> FROM <table_name1>
	UNION
	SELECT <column_name(s)> FROM <table_name2>
	
`UNION` selects only distinct values. To allow duplicate values use `UNION ALL`.

##Into
`SELECT INTO` can be used to create backup copies of a table.

	SELECT *
	INTO <new_table_name> [IN <external_database>]
	FROM <old_table_name>	
	//or only the columns we want instead of the * operator

A `WHERE` clause could be used to filter. And a `JOIN` can be used to copy from multiple tables.
