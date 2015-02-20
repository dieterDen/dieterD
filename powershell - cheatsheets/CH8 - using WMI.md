##CH8: Using WMI

de gewenste klasse zoeken in de namespace:

	- get-WMIObject -List "*bios*" | where name -match '^win32'

	or 

	- gwmi -List 'win32*bios*'

om meer properties te bekomen over bios, zoek in Types.ps1xml file:
	
	- select-string -Path $pshome\*.ps1xml -SimpleMatch "Win32_Bios"

Om deze extra properties te zien van de PSStatus set:

	- gwmi win32_bios | select psstatus

5. querying wmi: the basics

example :
	- gwmi win32_bios

6. Tell me everything about everything 
 
 example:

    - gwmi -class win32_share -Property * | format-list *
    
    beter is
    
    - gwmi -class win32_share
    
kan ook opgezocht worden via sql statement:

	- $query="select * from Win32_share"
	- gwmi -query $query
	
7. Tell me selected things about everything

geef enkel properties weer waarin je geïnteresseerd bent:

	- gwmi -query "select name from win32_share" |format-list name
	
	or 
	
	- gwmi  win32_share -property name |fl name 

8. Tell me everything about some things

	example:

	- $wmiquery="select * from win32_share where name='c$'"
	- gwmi -query $wmiquery |fl *

	or 

	-  gwmi win32_share -filter "name='c$'" |fl *

9. Tell me selected things about some things

example:

	- $query="select name, path from win32_share where name = 'users'"
	- gwmi -query $query | ft name, path