## Volledige documentatie php project 

# mysqli extensie toevoegen 

* Om mysqli te gebruiken -> extensie nodig: mysql.so
	- extension directory -> /usr/lib/php5/20121212
	- sudo apt-get install php5-mysql
	- na installatie:
	- sudo nano /etc/php5/apache2/php.ini
	- toevoegen van: extension=mysql.so 
	- opslaan
	- sudo /etc/init.d/apache2 restart
	- sudo /etc/init.d/mysql restart
	- eventueel heropstarten machine
 
# bij uploaden van file in php
	- param veranderen php.ini om van 8mb  upload volume te vergroten naar bv. 20mb. 
	- sudo nano /etc/php5/apache2/php.ini
	- ;Maximum allowed size for uploaded files.
	upload_max_filesize = 40M

	; Must be greater than or equal to upload_max_filesize
	post_max_size = 40M 



# RewriteEngine enable

* mod_rewrite is een apache module en geen php module. Om het te gebruiken in php -> gebruik cmd: EngineRewrite
* check of mod_rewrite enabled is:
	- ls /etc/apache2/mods_enabled | grep rewrite
	- -> als dit outputs: rewrite.load -> module enabled
	- zoniet-> doe:
	- a2enmod rewrite
	- service apache2 restart

# easyUI en data-grid
	- is jqeury plugin -> minder werk om tabellen en grids te maken
	
 
# JQuery EasyUI gebruiken in project:

	- ga naar: http://www.jeasyui.com/download/index.php
	- download GPL edition
	- plaats de inhoud in easyUI folder in uw project
	- om bijvoorbeeld drop-down navigation te creëren
	- gebruik code menubutton: http://www.jeasyui.com/documentation/menubutton.php
	- plaats deze in view class
	- voeg link en script elementen toe: 
	- link: easyUI/themes/default/easyui.css
	- link: easyUI/themes/icon.css
	- link: easyUI/demo/demo.css
	- script: js/jQuery.js
	- script: easyUI/jquery.easyui.min.js
	- script: easyUI/jquery.min.js

# Timezone instellen:

	- sudo nano /etc/php5/apache2/php.ini
	- date.timezone= Europe/Brussels
	- uit commentaar plaatsen
	- herstarten van httpd service vereist

# Uploaden file in Centos 6.5 -> prerequisites 
	- sudo vi /etc/httpd/conf/httpd.conf
	- bij <Directory "/var/www/html/extra"> 
	- toevoegen: AllowOverride All
	- toevoegen: Options Indexes FollowSymLinks
	- restart httpd.service
	(check of .htaccess file aanwezig is in folder van web applicatie)

# Installatie + gebruik apiGen

	- wget http://apigen.org/apigen.phar
	- chmod +x apigen.phar
	- sudo mv apigen.phar /usr/local/bin/apigen
	- sudo apigen --version
	- sudo apigen generate --help
	- sudo apigen generate --source [PATH TO DIR PROJECT] --destination [PATH TO TARGET DIRECTORY] --download --title "title" --todo --tree

# Character sets omzetten naar UTF-8 in php en mysql
	- php: 
	- sudo vi /etc/php5/cli/php.ini
	- uncomment: default_charset = "UTF-8"
	- save en restart service: apache2
	- controle via: phpinfo();
	- mysql:
	- sudo vi /etc/mysql/my.cnf
	- voeg volgende lijnen toe bij [mysqld]:
	- init_connect='SET collation_connection = utf8_unicode_ci'
	- init_connect='SET NAMES utf8'
	- character-set-server=utf8
	- collation-server=utf8_unicode_ci
	- skip-character-set-client-handshake
	- save and restart service: mysqld
	- controle via: mysql --user root -p
	- show variables like "collation_database";
	- show variables like "%character%"; 
	- show variables like "%collation%";
