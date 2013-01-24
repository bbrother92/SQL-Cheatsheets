#Constraints
Constraints are to limit the type of data that can go into a table. Constraints can be specified with the `CREATE TABLE` or with the `ALTER TABLE` statement.

	CREATE TABLE <table_name>(
		usage create..
	)
	
	ALTER <table_name>
	usage alter or usage drop..
<table>
  <tr>
    <th>Constraint</th>
    <th>Description</th>
    <th>Usage</th>
  </tr>
  <tr>
    <td><code>NOT NULL</code></td>
    <td>column will not accept <code>NULL</code> values</td>
    <td>Create: <code>columnname datatype NOT NULL</code></td>
  </tr>
  <tr>
    <td><code>UNIQUE</code></td>
    <td>Uniquely identifies each record in a table</td>
    <td>Create: <code>columnname datatype NOT NULL UNIQUE</code>
    	Alter: <code>ADD UNIQUE (columnname)</code><br>
    	Drop: <code>DROP CONSTRAINT columnname</code>
    </td>
  </tr>
  <tr>
    <td><code>PRIMARY KEY</code></td>
    <td>Uniquely identifies each record in a table, can only be one</td>
    <td>Create: <code>columnname datatype NOT NULL PRIMARY KEY</code>
    	Alter: <code>ADD PRIMARY KEY (columnname)</code><br>
    	Drop: <code>DROP CONSTRAINT pk_name</code>
    </td>
  </tr>
  <tr>
    <td><code>FOREIGN KEY</code></code></td>
    <td>A key that points to a PRIMARY KEY in another table</td>
    <td>Create: <code>columnname datatype FOREIGN KEY<br> REFERENCES tablename(columnname)</code><br>
    	Alter: <code>ADD FOREIGN KEY (columnname)<br> REFERENCES tablename(columnname)</code><br>
    	Drop: <code>DROP CONSTRAINT fk_name</code></td>
  </tr>
</table>
