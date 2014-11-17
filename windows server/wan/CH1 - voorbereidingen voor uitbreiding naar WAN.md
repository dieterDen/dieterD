##CH1: PFRTR lid maken van domain Poliforma.nl 

1. Toevoegen PFRTR aan AD 
    - Lid maken van domain POLIFORMA
    
2. Remote verbinding maken
    - Profiel van user lokaal maken door profile path te wissen bij Profile tabblad
    - User lid maken van domain admins
    - Op PFRTR bij server manager -> local server remote desktop-> enable -> select user
    - Op PFWS -> app: remote desktop connection -> show options -> PFRTR -> User name -> settings goedzetten -> open     
s
3. Een site koppelen aan een (sub)net
    - MMC Active Directory Sites & Services
    - New subnet