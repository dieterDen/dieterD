#Leveraging windows powershell providers

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

 -whatIf property -> gebruikt als je denkt de staat van het systeem te veranderen.

 


