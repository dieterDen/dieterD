##CH7 Using windows powershell remoting

all the commmands for remoting:

	- get-help * -parameter computername | sort name |ft name, synopsis -auto -wrap 

1. Configuring windows powershell remoting 
	
	op windows 8 staat WInRm( windows remote management) standaars uitgeschakeld

	- enable-PSRemoting -Force
	- controle via:
	- Test-WSMan -ComputerName w7c508

starting a remote windows powershell session

	- Enter-PSSession -ComputerName dc1

transcripts starten:

	- start-transcript
	- opgelet: werkt zowel in remote als local windows powershell console

remote verbinding voor één command

	- Invoke-command -ComputerName dc1 -ScriptBlock {gps | -last 1}

Invoke-command gebruiken voor meerdere computers:

	- $cn= "dc1","dc3","ex1"
	- $cred=get-credential iamred\administrator
	- invoke-commansd -cn $cn -cred $cred -ScriptBlock {gwmi win32_bios}

2. Creating a persisted connection

	- $dc1=new-PSSession -computername dc1 -credential iamred\administrator
	- enter-PSSession $dc1
	- verwijderen van session:
	- get-PSsession | remove-PSSession

credentials ingeven via

	- get-credential

example: setting up persisted session with multiple hosts:

	- $cred=get-credential -credential iamred\administrator
	- $cn="x1","dc1"
	- $ps=new-PSSession -ComputerName $cn -Credential $cred
	- invoke-command -session $ps -scriptblock {gsv | select -First 1}

3. Testing of powershell remoting is working

	- test-WSMan -computername dc1

onderzoek een win PSSession

	- get-PFSession -name testsession | fl *

remove session

	- get-PFSession -name testsession | remove-PFSession
