# DNS Cheatsheet

## Configuration files:
* /etc/named.conf
* /var/named

### 1) Configuratie DNS server

* yum install bind bind-utils -y
* Open: `/etc/named.conf`
  1. Aanpassen: listen-on port 53
  				allow-query
  2. eventueel aanpassen recursion
  3. Toevoegen zones

###2) Zone files aanmaken
    Maak een file aan voor de forward en de reverse zone aan in /var/named dir

### 3) Start DNS service
	* systemctl enable named
	* systemctl start named

###4) Firewall configuratie
    * firewall-cmd --permanent -add-port=53/tcp

###5) Herstart firewall
	* firewall-cmd --reload

###6) Configuratie permissies, SELinux
    * chgrp named -R /var/named
    * chown -v root:named /etc/named.conf
    * restorecon -rv /var/named
    * restorecon /etc/named.conf

###7) Test DNS
	* named-checkconf /etc/named.conf

###8) DNS server toevoegen in netwerk interface configuration files
	* vi /etc/sysconfig/network-scripts/...
	
pas /etc/resolv.conf aan:
	* nameserver   [ip-address]	