## Volledige documentatie php project 

# mysqli extensie toevoegen -> zie chapters connect met mysqli
 
# bij uploaden van file in php
	- param veranderen php.ini om van 8mb  upload volume te vergroten naar bv. 100mb. 


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
