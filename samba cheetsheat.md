configuring samba -> smb.conf
in /etc/samba/smb.conf OR
/usr/local/samba/lib/smb.conf

in smb.conf
-shares
-meta-services -> [global], printers

test your smb.conf file:
testparm /etc/samba/smb.conf