##Chapter 8: putting php to use

* cookie exists? -> isset()

* session_start -> creates or resumes a session 

* header("Location: ") -> functie om execution te veranderen naar ander script

	- vb. header("Location: signin.php ")

* append array to an existing disk file -> file_put_contents('namelist.txt',$entry, FILE_APPEND);

* get all content from disk file -> file_get_contents();

* check if textstring appears in a textfile -> strpos($namelist, $nameEntry); -> geeft cijfer terug

* how to reuse a snippet a code?
	- put it in a .php file
	- on every first line of a site page put: <?php require_once(entersite.php); ?>

* require_once of require -> the remaining script will not execute until code referenced by function is executed succesfully
* include_once of include -> does the same but does not halt the execution if the remaining script.

