## CH2 Het netwerk uitbreiden met een nieuwe site

1. Site PfHoorn toevoegen op PFSV1
    - MMC AD Sites & Services
    - Sites -> new Site
    - Subnet-> new subnet

2. De site link tssn twee sites

fysiek:

- Huurlijnen (T1, T3, E1, E3) via TSP (Telecommunicatie service provider)
- Telefoonverbindingen (circuit-switched):
    - analoog -> ongeschikt
    - ISDN (integrated Service Digital Network)
    - DSL (digital subscriber line) -> permanente verbinding
    - ADSL -> asymmetrical -> ongeschikt
    - HDSL & SDSL (high-bit-rate digital subscriber line & symmetrical digital subscriber line)
    - eigen verbinding (straal, glasvezel, copper-wired)

Nieuwe site link aanmaken:

MMC AD sites & services -> Inter-Site Transports -> new link

-> remove link: defaultipsitelink

Replicatie van AD over site link

new link -> properties -> Replicate every -> veranderen naar 15 minutes

tijd instellen van repliceren-> change shedule

3. RODC maken op nieuwe server (read-only)

    - nieuwe server toevoegen aan domain Poliforma.nl
    - nieuwe user aanmaken als gedelegeerd administrator account
    - AD installeren -> promote this server to a domain controller
    - ARS (administrator role seperation) -> beheer van RODC aan een gebruiker of  global security group 
    -> gebruiker kan AD wel niet bewerken
    
    Controle van RODC PFSV2:
    - in domain controllers van PFSV1 
    - in site PFHoorn aanwezig
   
Handmatig repliceren
    - MMC AD Sites & services
    - NTDS settings -> replicate now