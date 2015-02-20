## CH9 - Using CIM

CIM -> common information model

toepassingen:

	- query remote windows server 2012 computer
	- returns wmi information faster than gwmi
 	- promotes WMI discovery

1. using cim to explore wmi classes

example: search for wmi classes related to computers

	- get-CimClass -ClassName *computer*
	
2. finding wmi class methods

	- get-cimclass -classname process* -MethodName term*

3. filtering classes by qualifier

examples: 
	
	- get-cimclass -classname *computer* -qualifierName *update

	- get-cimclass * -qualifiername singleton methodname *

	-get-cimclass -classname *session* -qualifiername assoc*

4. Retrieving wmi instances

gebruik get-ciminstance to query for wmi data

example: 
	
	- get-ciminstance win32_bios

-> toont enkel de default properties in de xml file, om alle properties te tonen:

	- $b=get-ciminstance win32_bios
	- $b.CimClass.CimClassProperties | fw -name -Column 3

reducing returned properties and instances

use filter parameter to reduce number of returned instances

example:

	- gcim win32_service -Property name, state -Fil "name='bits'" |ft name ,state

5. Working with associations

example:

	- $logon= get-ciminstance win32_logonsession
	- get-cimassociatedInstance $logon |get-member

aanpassen van de resulting classes:

	- $logon= get-ciminstance win32_logonsession
	- get-cimassociatedInstance $logon -ResultClassName win32_useraccount

OPGELET: bij get-cimassociatedinstance mag het inputobject maar 1 single instance hebben anders error
-> werk met array indexing:

	- $disk=get-ciminstance win32_logicaldisk
	- get-cimassociatedinstance $disk[0]

beter is om arrays te vermijden

	- $disk=get-ciminstance win32_logicaldisk -filter "name='c:'"
	- get-cimassociatedinstance $disk

om de objecten beter weer te geven die get-cimassociatedinstance terug geeft gebruik typename:

	- get-cimassociatedInstance $disk |get-member | select typename -Unique

toon vervolgens de associaties die teruggeven worden

	- get-cimassociatedInstance $disk -resultClassName win32_directory

toon de informatie van de wmi class 

	- $dp=get-cimassociatedinstance $disk -resultclassname win32_diskpartition
	- $dp |FT deviceID, BlockSize -Autosize
 
 


