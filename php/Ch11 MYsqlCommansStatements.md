##Chapter 11 - Mysql command statements

# Assignments operators

* vb. @name:= 'Michael'
	- of set @name = 'michael'

* comparison functions 
	- coalesce() -> gives the first non-null arguments
	- interval() -> geeft index van het argument dat minder in waarde is dan zijn volgend
	- strcmp(string1,string2) -> -1 als string 1 voorkomt in string2, geeft 0 als strings gelijk zijn aan elkaar, geeft -1 als strings verschillen
	
* control flow functions pag 358
	- case
	- if ... else ...
	-  ifnull()
	- nullif()-> return null if value1 eaquals value2

* date and time functions
	- now() -> returns date and time
	- adddate(date,days) -> add days to date
	- date_format(date,format) 
	- curdate()/curtime() -> returns current date and time
	- datediff(date1,date2)-> return number of days after subtracting the two dates
	- zie pag 360.

* Encryption and compression 
	- aes_decrypt -> using AES decryption
	- aes_encrypt
	- compress(string)
	- zie pag 363
	
* string functions
	- pag 364-365
	- substr() 
	
* Overige functies:
	- current_user()/ user() -> user name and host name
	- database()/schema() -> name of current db
	- row_count()-> number of rows updated
	- zie pag 365
	
# SQl commands and reserved words

	- limit -> limits the number of rows returned from a query
	- insert/replace
	- alter database -> change character set and collation sequence
	
* Using events
	- turn event scheduler on 
	1) set global event_scheduler=ON;
	2) show processlist;

	- create event event_name on schedule shedule do mysql-statement;
	- drop event event_name;
	- pag 397

* using views
	- create view view_name as select_statement;
