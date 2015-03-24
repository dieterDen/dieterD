## Overzetten directory van host naar guest via ssh

	1) sudo apt-get install openssh-server


	2) enable root password om ssh te gebruiken:
		- /etc/ssh/sshd_config
		- PermitRootLogin yes
		- service ssh restart

	3) op host 
		- passwd instellen

	4) op guest: 
		- scp -P 22 -r root@192.168.50.197:/home/[USER]/NetBeansProjects/NetbeansProject/* .
		- 192.168.50.197 -> ip address van host