## CH2 - using win PS cmdlets

4 belangrijke commando's:

	- Get-Help
	- Get-Command
	- Get-Member
	- Show-Command

1. commin PS parameters:

	- -Verbose -> gives additional information during execution of a command
	- -ErrorAction -> wat te doen bij een error

2. Win PS Transcript

	- start-transcript -> houdt alle errors, output, ... bij
	- stop-transcript

3. Help topics

	- Get-Help Get-Process -> komt overeen met een man-page
	- Get-Help Get-Process -Examples

Meer info krijgen per pagina

	- Help -Full -Name Get-WinEvent
	
4. Using get-help to search for cmdlets

	- Get-Help *process
	- Get-Help *process - Category cmdlet

Info opzoeken over een concept in PS:

	 - Get-Help -Name wmi -Category HelpFile

5. using get-command to find cmdlets

	- get-command -verb get
	- get-command -verb get -Noun *tcp*
	- get-command -verb get -Noun *ip* -Module NetTcpIp

6. Using Get-Member

	-> gives propeties of an object

7. Show-Command

-> gives a graphical input for a command
	  
	  - show-command get-process

8. Setting the Script execution policy

	- Get-ExecutionPolicy -List
	- Set-ExecutionPolicy unrestricted

9. creating a new win ps profile

	 - New-Item $Profile -Itemtype file -Force
