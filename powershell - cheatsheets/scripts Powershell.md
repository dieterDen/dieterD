# scripts Windows Powershell

1.

Function Get-IPObject ([bool]$IPEnabled =$true)
{
Get-WmiObject -Class Win32_NetworkAdapterConfiguration -Filter "IPEnabled =$IPEnabled"
}

Function Format-NonIPOutput($IP)
{
Begin {"Index # Description" }
Process {
    ForEach ($i in $IP)
    {
    Write-Host $i.Index `t $i.Description
    }
}
}

$IP=Get-IPObject -IPEnabled $false
Format-NonIPOutput($ip)


2.


Function Get-OperatingSystemVersion 
{
	(Get-WmiObject -Class Win32_OperatingSystem).Version
}

"This os is version $(Get-OperatingSystemVersion)"


3.

Function Get-TextStatistics($path)
{
	Get-Content -path $path |
	Measure-Object -line -character -word
}

Get-TextStatistics -p "C:\fso\mytext.txt.txt"