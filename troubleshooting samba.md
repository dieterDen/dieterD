##Samba troubleshooting

1)
Log files:
	- /usr/local/samba/var/smbd.log
	- /usr/local/samba/var/nmbd.log

2)
ping 127.0.0.1 -> No IP networking installed

3)
ping localhost -> check /etc/hosts

4) Test TCP met FTP
 	- ftp server

5) smbd and nmbd draaiend?
	- systemctl status nmbs
	- systemctl status smbd

6) lokaal testen met smbclient:

	- smbclient -L localhosrt -U%
-> toont shares van de server

7) nmblookup
	- nmblookup -B naam_server __SAMBA__ 
	
	->netbios name service werkt?
	-> nmbd draait?
	
8) DNS 

	- nslookup name
	
	-> check anders /etc/resolv.conf

	
9) check firewall

	- firewall-cmd --permanent --zone=public --add-service=samba

10) check sabam settings

	- testparm