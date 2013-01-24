#Views
A view is a virtual table.

##Create

	CREATE VIEW <view_name> AS
	SELECT <column_name(s)>
	FROM <table_name>
	WHERE <condition>

##Update

	ALTER VIEW <view_name> AS
	SELECT <column_name(s)>
	FROM <table_name>
	WHERE <condition>
	
##Drop

	DROP VIEW <view_name>