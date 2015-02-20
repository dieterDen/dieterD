#CH6 Leveraging windows powershell providers

## default providers on a default installation

Get-PSProvider

##The alias provider

### create new alias

`set-location alias:`
`new-item -name Processes -Value get-process`

### remove alias
´remove-item .\Processes`

you must be in the PS Alias dir

### make new alias with cmdlets -> zie overzicht
Get-Commmand -Noun alias |select name

* remove alias:

example: Remove-Item -Path Alias:\myservice

## The certificate provider

Open certificates MMC
`Invoke-Item cert:`

### searching for certificates
 `dir Cert:\CurrentUser -Recursive | ? subject -match 'test' `

 -whatIf property -> gebruik als je denkt de staat van het systeem te veranderen.
 
 - finding expiring certificates

 use property ´notafter´ van certificate object

 example: ´dir .//CurrentUser -Recurse |where notafter -lt "5/1/2012" ´

- cerificates expiring in 30 days

in Cert dir: ´Get-ChildItem -Recurse -ExpiringInDays 30 ´

##Environment provider

gives access to system environment variables

-to see value of a variable: ´echo %windir%´

alternatief: `Get-Item windir` -> in env dir

-listing of environment variables: 

´Set-location env:´
´dir`

-> alternatief voor dir: ls, gci (Get-childItem)

##File System Provider

gives acces to the file system

example create neww folder
`new-item -path C:\samplefolder -itemtype directory`

or 

´new-item -path C:\samplefolder -itemtype directory | out-null´

-> reduces the output

navigeren naar folder:

	- Set-location C:\samplefolder

toevoegen tekst aan file:

	- add-content -path .\samplefile.txt -value "this is text"

lezen van file:

	- get-content -path .\samplefile.txt

verwijderen dir + inhoud

	- remove-item C:\samplefolder -Recurse

## function provider

gives access to the functions defined in PS

lijst van functies:

	- get-childItem function:

inhoud van functie zien:(vb prompt functie)

	-get-content Function:\promt

## Registry provider

gives access to registry on the local system

tonen van de twee registry drives:

	- get-PSDrive -PSProvider registry | select name,root

create new registry drive

	- new-PSDrive -PSProvider registry -Root HKEY_CLASSES_ROOT	 -Name HKCR

locate to new drive:

	- Set-location HKCR:

toegang tot info van nieuwe registry:

	- get-childItem
	-dir

opvragen registry values en waarde van properties gebruik:

	- get-item
	- get-itemProperty

create new registry key

	- new-item -path HKCU:\software  -Name test -Force

setting the default value for the key:

	- set-item -path HKCU:\software\sample -value "sample key"
	- -> met "sample" de registry key in de folder "software"

Alles in één commando:

	- new-item -path hkcu:\software\sample -value "dafault value"

Aanpassen van de waarde van een registry property value

	- set-itemProperty -path HKCU:\software\test -Name newproperty anewvalue

een ontbrekende registry property key
	
	- if((get-itemProperty HKCU:\software\sample -Name bogus -ea 0).bogus) {'property already exists'}
	  else {set-itemProperty -path HKCU:\Software\sample -Name bogus -value 'initial value'}

## variable provider

gives access to the variables

alle cmdlets over variables opvragen via

	- get-help *variable | where-object {$_category -eq "cmdlet"} | format-list name, category, synopsis
	




