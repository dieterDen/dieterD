## PHP beginner's guide

* begin met <?php ?>

* output van characters via 
	- echo -> neemt meerdere argumenten aan
	- print

* use backslash \ als escape sequence

* data type resouce -> een referentie naar een extern element. Gebruikt met MySQl!

* Variables -> start altijd met $-sign

* operators: 
	
	- === -> check of dat variaben identiek zijn

	- == -> check of dat 2 vars equal zijn

* arrays:
 - functions: count(), array(), print_r()-> indien tweede param=true, geeft elementen terug ipv te tonen.

* tijd:
	- functies:
	- getdate()
	- date(), vb: echo date(DATE_RFC822); of echo date("l,F jS, Y");
	- time()

# zie pag. 219 voor meer formatting codes van date

* string function:

	- implode() or join() -> zet array elements samen in een string: vb. implode(" ",$nameEntry)

* foreach statement -> gebruikt om te itereren over array en objects
	- foreach ($array as $value){}
	- foreach ($array as $key => $value){}

* file function:

file connection= file pointer
	- fopen() -> open a file
	- fwrite()
	- fread() -> read # bytes from file into string var
	- fclose() -> eindig file pointer
	- fseek() -> verandert de file pointer van positie
	- fgetc() -> leest een character in van een open file
	- ftell() -> geeft huidige positie van file pointer weer.
	- fgets() -> reads a line from a open file
	- file () -> leest volledige text file in een array

* Superglobals:
	- $_SESSION -> session_start()  (pag. 248)
	- $_SERVER -> array met informatie over de server
	- $_COOKIE -> setcookie() -> vb. setcookie(name[,value[,expire [,path [,domain [,secure [,httponly]]]]]]);
	
* strpos() -> vind de positie van het eerste voorkomen van een substring in een string
 
