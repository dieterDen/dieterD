## CH3: Werkstations in de vestiging Hoorn

1. Nieuwe DHCP scope aanmaken

    - ip-ranges toevoegen van IPv4 netwerk van Hoorn
    - SuperScope maken bestaande uit de netwerken van Hoorn en Budel
    - controle op werkstation: ipconfig /all en op PFSV1 address leases

2. Routers, broadcasts, DHCP en DHCP relay agents

routers houden broadcasts tegen

indien router RFC 1552 compliant -> DHCP discovers worden doorgelaten

= DHCP relay agent protocol

DHCP relay agent installeren via de role: `Routing and remote access`
    - general -> new routing protocol
    - DHCP relay agent -> new interface -> connectie Hoorn selecteren

 DHCP server aangeven van netwerk Budel:
     - DHCP relay agent->properties -> add server
