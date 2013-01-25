#Functions
##Dates
<table>
	<tr>
		<th>Function</th>
		<th>Description</th>
	</tr>
	<tr>
		<td><code>GETDATE()</code></td>
		<td>Returns current date and time</td>
	</tr>
	<tr>
		<td><code>DATEPART(datepart,date)</code></td>
		<td>Returns single part of a date/time.</td>
	</tr>
	<tr>
		<td><code>DATEADD(datepart,number,date)</code></td>
		<td>Adds or subtracts specified time from a date</td>
	</tr>
	<tr>
		<td><code>DATEDIFF(datepart,startdate,enddate)</code></td>
		<td>Return time between two dates</td>
	</tr>
	<tr>
		<td><code>CONVERT(data_type(length*),<br>&nbsp; expression,style)</code>
		</td>
		<td>Displays date/time data in different formats <em><small>(data_type is output data_type *optional length. expression is value to be converted. style is the output format.)</small><em></td>
	</tr>
</table>
<table>
  <tr>
    <th>datepart</th>
    <th>Abbreviation</th>
  </tr>
  <tr>
    <td>year</td>
    <td>yy, yyyy</td>
  </tr>
  <tr>
    <td>quarter</td>
    <td>qq, q</td>
  </tr>
  <tr>
    <td>month</td>
    <td>mm, m</td>
  </tr>
  <tr>
    <td>dayofyear</td>
    <td>dy, y</td>
  </tr>
  <tr>
    <td>day</td>
    <td>dd, d</td>
  </tr>
  <tr>
    <td>week</td>
    <td>wk, ww</td>
  </tr>
  <tr>
    <td>weekday</td>
    <td>dw, w</td>
  </tr>
  <tr>
    <td>hour</td>
    <td>hh</td>
  </tr>
  <tr>
    <td>minute</td>
    <td>mi, n</td>
  </tr>
    <tr>
    <td>second</td>
    <td>ss, s</td>
  </tr>
  <tr>
    <td>millisecond</td>
    <td>ms</td>
  </tr>
  <tr>
    <td>microsecond</td>
    <td>mcs</td>
  </tr>
  <tr>
    <td>nanosecond</td>
    <td>ns</td>
  </tr>
</table>

##NULL
The `ISNULL()` function is used to specify how to treat `NULL` values.

	SELECT ISNULL(<column_name>,0) FROM <table_name>
	//if there is a null value in the column it will 
	//be replaced with a zero

##Aggregate functions
<table>
  <tr>
    <th>Function</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>AVG(column_name)</code></td>
    <td>Returns the average value of a numeric column</td>
  </tr>
  <tr>
    <td><code>COUNT(criteria)</code></td>
    <td>Returns the number of rows that matches a specified criteria. <small>example SELECT COUNT(*) FROM <table_name></small></td>
  </tr>
  <tr>
    <td><code>FIRST(column_name)</code></td>
    <td>Returns the first value of the selected column</td>
  </tr>
  <tr>
    <td><code>LAST(column_name)</code></td>
    <td>Returns the last value of the selected column</td>
  </tr>
  <tr>
    <td><code>MAX(column_name)</code></td>
    <td>Returns the largest value of the select column</td>
  </tr>
  <tr>
    <td><code>MIN(column_name)</code></td>
    <td>Returns the smallest value of the select column</td>
  </tr>
  <tr>
    <td><code>SUM(column_name)</code></td>
    <td>Returns the sum of a numeric column</td>
  </tr>
</table>
The `GROUP BY` statement is used to group the result-set by one or more columns. Often needed with aggregate functions.

The `HAVING` clause was adde to SQL because the `WHERE` keyword could not be used with aggregate functions.

	SELECT <column_name>, <aggregate_function(<column_name>)>
	FROM <table_name>
	WHERE <column_name> <operator> <value>
	GROUP BY <column_name>
	HAVING <aggregate_function(<column_name>)> <operator> <value>
##Scalar functions
<table>
  <tr>
    <th>Function</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>UCASE()</code></td>
    <td>Converts value to uppercase</td>
  </tr>
  <tr>
    <td><code>LCASE()</code></td>
    <td>Converts value to lowercase</td>
  </tr>
  <tr>
    <td><code>MID(column_name,start[,length])</code></td>
    <td>Used to extract characters from a text field. <small>starts at 1, length is optional, when omitted function returns the rest</small></td>
  </tr>
  <tr>
    <td><code>LEN(column_name)</code></td>
    <td>Returns the length of the value in a text field</td>
  </tr>
  <tr>
    <td><code>ROUND(column_name,decimals)</code></td>
    <td>Rounds a numeric field to the number of decimals specified</td>
  </tr>
  <tr>
    <td><code>FORMAT(column_name,format)</code></td>
    <td>Format how a field is displayed</td>
  </tr>
</table>
