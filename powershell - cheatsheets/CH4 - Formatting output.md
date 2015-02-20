## CH4 - formatting output

	- table -> format-table (ft)
	- list -> format-list (fl)
	- wide display
	- output grid

1. table

	- Get-process | format-table -Property name, handles, vm
	- Get-process | format-table -Property name, handles, vm -autoSize
	- Get-process | format-table -Property name, handles, vm -autoSize -wrap

	-> wrap wordt gebruikt om om te gaan met lange namen

2. list

	- get-eventlog -name application -newest 5 | format-list -property source, entrytype

3. wide display

	- get-process | format-wide -property name -autosize
	- get-process | format-wide -property name -Column 4

4. creating an output grid

	- gps |out-gridview
