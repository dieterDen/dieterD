## CH12: Working  with functions

example function:

Get-OperatingSystemVersion.ps1

Function Get-OperatingSystemVersion 
{
	(Get-WmiObject -Class Win32_OperatingSystem).Version
}

"This os is version $(Get-OperatingSystemVersion)" 

Voor de naam van functies: gebruik zoveel mogelijke de bestaande verbs in PS

1. Parameters meegeven aan functies;

	- Get-Textstatistics("C:\fso\text.txt")
	- Get-Textstatistics -Path "C:\fso\text.txt"
	- Get-TextStatistics "C:\fso\text.txt"

example:

Get-TextStatistics function

Function Get-TextStatistics($path)
{
	Get-Content -path $path |
	Measure-Object -line -character -word
}

2. Using a type constraint

Om er voor te zorgen dat de parameters van een functie het juiste type data krijgen.

Om een aangepaste foutboodschap weer te geven na verkeerde data input: use TRAP

Trap [SystemException] {"Error trapped" ; continue}

3. Using multiple parameters

using the param statement inside the function

TIPS:

Maak aparte functies voor:

	- collecting data
	- display information

Maak gebruik van:	

	- Begin {}--> geeft header
	- Process {}