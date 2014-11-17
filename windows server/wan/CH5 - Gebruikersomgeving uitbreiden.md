## Gebruikersomgeving uitbreiden

OP PFSV2:
	- nieuw datavolume met ingeschakelde compressie
	- everyone verwijderen uit ntfs permissies
	- role service installeren: file and storage services
	- folders aanmaken: UserFolders, UserProfiles, AfdelingsFolders, AfdelingsFolders/OnderafdelingFabricageHoorn
	
Op PFSV1:
	- In AD OU FabricageHoorn aanmaken in OU Productie
	- global security group: FabricageHoorn
	- global group Productie is lid van global group FabricageHoorn
	- global group frabricageHoorn lid van global group fabricagebudel
	- global group fabricagebudel lid van fabricageHoorn
 	- global group FabricageHoorn lid van waarvan alle global gebruikersgroupen lid van zijn.
  	- maak aan:T_OnderafdelingFabricageHoorn (local group)
  	- FabricageHoornlid van domain local T_OnderafdelingFabricageHOORN

  	- beveiligde toegang regelen via het AGDLP-principe
  	- repliceer handmatig AD
  	- share folder OnderafdelingFabricageHoorn + permissies

 1. gebruikers aanmaken

 	- account aanmaken, naar OU verplaatsen (op PFSV1)
 	- tip: gebruik copy van bestaande accounts
