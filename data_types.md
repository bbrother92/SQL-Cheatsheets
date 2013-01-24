#Data types

##Text
	char
	varchar(<max_number_characters>)
	
	text
	
	//unicode character strings
	nchar
	nvarchar
	ntext

##Numbers
###Exact numbers

	int
	int unsigned		//only positive numbers
	
	int auto_increment
	//when not given a value, default to highest value in column + 1
	
	bigint
	smallint
	tinyint
	
	bit
	
	decimal
	numeric
	decimal(precision, scope)
	//precision = total max char | scope = max char after decimal point
	
	money
###Approximate numbers

	float
	double
	real
###Date & time

	date		// 'YYYY-MM-DD'
	time		// '[H]HH:MM:SS'
	datetime	// 'YYYY-MM-DD HH:MM:SS'
	smalldatetime
###Binary strings

	binary
	varbinary
	image
###Other

	cursor
	sql_variant
	table
	timestamp
	uniqueidentifier (GUID)
###Booleans

	bool
	boolean