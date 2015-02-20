## CH10 Using the win PS ISE

ISE -> integrated scripting environment

1. use of ISE snippets

ctrl + j 

2. creating new snippets

gebruik new-IseSnippets

	-get-ISESnippet | ? name -NotMatch 'switch' |remove-item -WhatIf
	-get-ISESnippet | ? name -NotMatch 'switch' |remove-item 


3. script-execution-policy

	- get-executionpolicy
	- set-executionpolicy