##CH4: Gebruik en beheer op afstand met een VPN

externe verbindingstechnieken
    - inbelverbinding
    - VPN verbinding

1. VPN-server PFRTR
    - MMC routing & remote access
    - -> disable routing and remote access
    - -> configure and enable routing and remote access
    - -> kies VPN and NAT
    - -> configureer DHCP relay agent opnieuw met ip adres van dhcp server
    - controle: address leases op PFSV1 aan PFRTR voor toekomstige VPN connecties
 
2. VPN configureren

Authenctication methods: 
	- EAP -> extensible authentication protocol
	- PAP -> password authentication protocol
	- CHAP -> Challenge handshake authentication protocol
	- MS-CHAP v2 -> werkt niet op niet-windows clients
  
Uitwerking op PFRTR:
	- PRTRT-> routing and remote acces -> properties-> security -> authentication methods
	- Kies voor MS-CHAP v2
	
VPN protocollen:
	- PPTP-> point to point tunneling protocol
	- L2TP-> Layer two tunneling protocol
	- SSTP -> secure socket layer protocol
	- IKEv2 -> Internet key exchange v2      

Poorten van VPN protocollen bekijken en bewerken -> Routing and remote access
	- properties van Ports -> alle poorten uitschaken behalve PPTP
	- PPTP port instellen: configure -> remote access connections (inbound only) + max ports: 1

Toestemming geven om VPN te mogen gebruiken:

PFSV1: account van uzelf selecteren-> tabblad dial-in -> allow access

3. VPN op PFWS1
login als: PCGebruiker1
	- control panel-> networking and sharing center -> set up a new connection
	- VPN connection -> IP: 192.168.101.1 ,name ingeven
	- inloggen via: POLIFORMA\Jan_Sme

4.VPN op werkstation afstemmen op VPN server
Op PFWS -> networking and sharing centrum -> link VPNPoliforma-> VPNPoliforma status
	- -> properties -> security -> Type of VPN: PPTP
	- select MSCHAP v2 
	- tabblad networking -> schakel IPv6 uit

Controle werking VPN:

PFRTR-> routing and remote access -> Remote access clients

5. VPN-verbinding gebruiken:

	- als gebruiker:
	- gebruik VPNPoliforma
	- toegang tot shared folders and shared printers

	- als beheerder:
	- maak een remote verbinding -> username: POLIFORMA\uzelf -> selecteer: drives
	- tabblad experience: LAN(10MBps or higher)
	