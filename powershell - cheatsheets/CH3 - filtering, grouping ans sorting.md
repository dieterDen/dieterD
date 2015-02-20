##CH3 - Filtering, grouping and sorting

sorting:

	- ...| sort -Property status
	- ...| sort status
	- ...| sort status -Descending

grouping:

	- ...| sort status | group status
	- ...| sort name |group name -NoElement | sort count -Descending
	
filtering:

	- ...| where vm -gt 1000MB

filtering on the left:

-> compare:

	- Get-Eventlog -Logname application | where entrytype -eq 'error'
	- Get-Eventlog -Logname application -EntryType error
	
 


