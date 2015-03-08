##CH12- using a mysql database with php

# database manipulation

	- mysqli_close() -> closes connection with db
	- mysqli_connect("localhost","root","password","shop")
	- mysqli_query($conid, $QUERY);
	- mysqli_fetch_assoc() -> gives associative array with field names as the indexes.
	- mysqli_fetch_row() -> gives enumerated array with field numbers as the index from a row
	- pag 407.

# Connectie maken met mysqli_connect !!!
	
* Om mysqli te gebruiken -> extensie nodig: mysql.so
	- extension directory -> /usr/lib/php5/20121212
	- sudo apt-get install php5-mysql
	- na installatie:
	- sudo nano /etc/php5/apache2/php.ini
	- toevoegen van: extension=mysql.so 
	- opslaan
	- sudo /etc/init.d/apache2 restart
	- sudo /etc/init.d/mysql restart
	- eventueel heropstarten machine
	
* Om te zoeken in nano editor
	- ctrl + w
	- volgend item: alt + w

* database information

	- mysqli_affected_rows() -> number of rows affected of an operation
	- mysqli_errno() -> gives error number
	- mysqli_error() -> gives error message
	- mysqli_info -> gives info about last query
	- zie pag. 413

* Database administration functions
	- mysqli_data_seek() -> moves row pointer to specified row
	- mysqli_field_seek() -> sets result pointer to specified field number
	- zie pag. 414

# Form handling and php

* To check if form is submitted, use:
	- $_post['submit'] -> superglobal element

* action method in form, can be used to return to php code
	- action=<?=$_SERVER['php_self']?> -> is php snippet code

* when sending strings to the database always use:
	- mysqli_real_escape_string($conid,$_post['title']);
	-> places backslashes in front of  special characters

# improving security
	- htmlentities() -> convert html -> html entities
	- strip_tags() -> removes tags
	- voorbeeld pag. 422

