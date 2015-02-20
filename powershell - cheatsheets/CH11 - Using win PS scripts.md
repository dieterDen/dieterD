## CH11 - powershell scripts

run a script as a scheduled job: 2 modules available
	- ScheduledTask
	- PSScheduledJob

script opslaan als: .PS1 extension

run a script:

	- drag the file to the PS console
	- paste the path of the script in the PS console
	- maak gebruik van de NoExit -parameter

script oproepen via PowerShell.exe:

	- run -> powershell -noexit -file c:\fso\test.ps1

1. Enabling win PS scripting support

 six levels of execution policy:
    
    - restricted
    - Allsigned
    - remoteSigned
    - unrestricted
    - bypass
    - undefined

three execution policy scopes:

	- Process
	- CurrentUser
 	- localMachine

totaal overzicht via:

	- get-executionPolicy -List

    
    - set-executionPolicy unrestricted
    - get-executionPolicy

2. Transitioning from command line to script

als script faalt doordat cmdlet faalt , kan er toch doorgegaan worden via -ErrorAction parameter. Deze kan 4 waarden aannemen:

	- silentlyContinue
	- continue
	- inquire
	- stop

output van een script verzorgen:

example:

	- ... | stop-process -passthru  | foreachobject {$_.name + 'with process id: '+ $_.ID + 'was running'}

toewijzen van meerdere waarden aan een variable van een script:

	- $process="notepad","calc"

3. Understandig variables and constants

variable opvullen:

	- $process= get-process

4. While statement

DemoWhileLessThan.ps1
$i=0
While ($i -lt 5)
{
	"`$i equals $i"
	$i++
}	 # end while

ander voorbeeld

WhileReadLine.ps1
$i = 0
$fileContents =Get-Content -path C:\fso\testfile.txt
While ($i -le $fileContents.length)
{
	$fileContents[$i]
	$i++
}

-> dit doet hetzelfde als : get-Content

Tip: zoeken voor de alias voor get-content

	- get-alias -Definition get-content

5. Do..While statement

DemoDoWhile.ps1
$i = 0
$ary = 1..5
do 
{
	$ary[$i]
	$i++
} while ($i -lt 5)

DisplayCapitalLetters.ps1
$i= 0
$caps=65..91
do
{
	[char]$caps[$i]
	$i++
}while ($i -lt 26)

6. Do ..Until statement

DemoDoUntil.ps1
$i=0
$ary=1..5

Do
{
	$ary[$i]
	$i++
} until ($i -eq 5)

7. For statement

DemoFor.ps1
$i=0
For(; $i -lt 5;)
{
	"`$i is equal to $i"
	$i++
}

for (;;) -> geeft infinite loop

8. ForEach statement

demoForEach.ps1
$ary=1..5
Foreach ($i in $ary)
{
	$i
}

ending ForEach statement: Break

demoBreak.ps1
$ary=1..5
forEach($i in $ary)
{
	if ($i -eq 3) {	break }
	$i
}
"statement following foreach loop"

-> exit kan ook gebruikt worden om script te stoppen

foreach kan ook gebruikt worden op win PS console:

	- 1..5 | ForEach-Object {$_}

9. using the if-statement

demoIfElse.ps1
$a=4
if ($a -eq 5)
{
	'$a equals 5'
}
else
{
	'$a is not equal to 5'
}

10. Switch statement

DemoSwitchMultiMatch.psi
$a=2
Switch ($a)
{
1 { '$a = 1'}
2 { '$a = 2'}
2 { 'Second match of the varaible $a'}
3 { '$a = 3'}
Default { 'Unable to determine value of $a '}
}

example:

DemoSwitchArrayBreak.psi
$a=2,3,5,1,77
Switch ($a)
{
1 { '$a = 1' ; break}
2 { '$a = 2' ; break}
3 { '$a = 3';break }
Default { 'Unable to determine value of $a '}
}
