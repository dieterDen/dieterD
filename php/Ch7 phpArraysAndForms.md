##Chapter 7: PHP arrays  and forms

* method1: 
	- $cars[0]="Ford";
	- $cars[1]="BMW"

* method 2:
	- $cars=array(0=>"Ford",1=>"BMW");
	
* method 3
	- $cars=array("Ford","BMW");

* the array operator: =>

* add value to operator at end:
	- $cars[]="GM"

* Delete value from array:
	- $cars[3]=" ";

* looping an array with while lus:
	- gebruik makend van: list() en each()

# navigating in arrays
	- current() -> gives value of current position of pointer in array
	- key() -> returns key value on the position of the pointer
	- next()
	- prev()
	- end()
	- reset()

# converting an array
	- implode()-> convert from array to string
	- explode() -> convert from string to array

# joining and splitting arrays
	- union
	- array_merge() -> joins the values and renumbers the keys
	- array_combine() -> joins an array of keys with an array of values

# splitting and rearranging arrays
	- array_slice() -> removes elements from an array
	- array_chunk() -> divides an array into equal-sized chunks
	- array_splice() -> removes a sequence of elements and provides for insertion of an replacement array.
	- array_flip() -> exchanges keys and values.

#comparing arrays:

	- equality -> ==
	- identity -> ===
	- inequality -> !=, <>
	- non-identity -> !==
	- array_diff()
	- array_diff_assoc()
	- array_intersect()
	- array_intersect_assoc()

# handling multidimensional arrays
	
	$contacts=array(
		$sue=> array( "email"=> "sue.com"),
		$tom=> array("email"=>"tom.com"));
	
* tonen van data -> gebruik 2xforeach loops

# extracting form data from an array

	- gebruik van superglobal arrays -> $_GET, $_POST, $_REQUEST
