## CH13 - Registering and responding to users

* template(html) -> voor altijd dezelfde layout te gebruiken in een webapplicatie

* In begin van script, plaats: session_start()
	- anders kan je niet de $_session[] global variabele gebruiken

* checken of formulier correct ingevuld is met php:
	- $_session["errmsg"== 1] -> check of eerste veld correct ingevuld is

* nieuw cookie aanmaken met gegevens van form
	- setcookie("Admin[name]",$name,$expire,"/");
	- laatste param: "/" staat voor path in de server maw "/" héél het domein

* delete cookie
	- pag. 454


* bij tonen van datum
	- gebruik: strtotime() -> will parse a date in an unix timestamp
	
* string als getal opslaan in database anders error in database:
	- $cost+0 -> forces php to convert to number
	- (float)$_post['class_cost'] -> converts to float

* passing info to php script
	- via the url -> gebruikt GET method not very safe
	- use a hidden field and post -> a bit safer
	- onsubmit="return validate_form(this);" ...>
	-<input type="hidden" name="classid" value="<?php echo $classid; ?>"/>
	- zie pag. 481

* adding a payment system:
	- go to: paypal.com -> business -> need to accept credit cards -> On your website

	
* Row uit table als object gebruiken:
	- $row=mysqli_fetch_object($result);
	- $db_userid=$row->admin_id;

* tonen van rijen van tabel in  browser
	- use while lus
	- <?php while ($classrow =mysqli_fetch_assoc($result))
	{ ?>
	<tr>
		<td>
			<a href="classdelete.php?recordID=<?php echo $classrow ['class_id']; ?>">Delete</a>
		</td>
	</tr>

	}

	- recordID wordt gebruikt in Get method to pass on class_is
	- $classid=($_get['recordID']);

