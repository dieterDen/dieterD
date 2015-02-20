#CH5 Storing output

## store data in text file

* redirect and append

use >> operator

example: Get-Volume >>c:\fso\volumeInfo.txt

* redirect and overwrite

use > operator

example: Get-Volume >c:\fso\volumeInfo.txt

* Controlling the text file
 
 use Out-File operator
 
 example: Get-Service | Format-Table Property * -Force -Auto | Out-File c:\fso\WideServoces.txt -Encoding UTF8 -Width 500

## Store date in .csv file

use Export-Csv operator 
	 
	 `optie: NoTypeInformation -> no line of information at the top of the file`

example: get-process | export-csv -Path c:\fso\process.csv -NoTypeInformation

## Store data in XML
to store complex objects

use Export-Clixml operator

example: get-process | export-clixml -path c:\fso\processXML.xml

* reconstitute the object from a offline .xml-file

example: $xml = import-clixml -Path C:\fso\processXML.xml

to view the name of the first object:
 $xml[0].name



