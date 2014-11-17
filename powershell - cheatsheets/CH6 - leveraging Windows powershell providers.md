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






