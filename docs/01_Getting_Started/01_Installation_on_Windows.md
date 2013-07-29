You will need to download first these softwares :

* Web server like [XAMPP](http://www.apachefriends.org/fr/xampp-windows.html)
* Dependency Manager for PHP : [Composer](http://getcomposer.org)
* The last version of VieAssociative
* An IDE like Sublime Text


## File installation
Create a folder on your web server directory.
Uncompress the VieAssociative code on there.  

	Exemple : web_server_root/your_vieassoc_folder/app for the app folder.

Hold the SHIFT key while you right-click the Windows window. You should see "Open Command Window here"

1. On this command window, type : 

        composer install

2. Then 

        composer update

Repeat the last command meny times until nothing is affected. Keep this cmd window open.

## Database installation

Create a database with PhpMyAdmin.
Update the file web_server_root/your_vieassoc_folder/app/config/local/database.php with corresponding values.

## Host file configuration
It will allow you to reach the website with an other URL than localhost. You can use wathever you want, but I personnally use **.vieassoc.lo**
The file is located on YOUR_SYSTEM_LETTER:\Windows\System32\Drivers\etc and the file is **hosts** . You may need some tricks for editing it because it's a system file, so copy paste this file anywhere else, edit it, and replace it where you found it.

	
	127.0.0.1 www.vieassoc.lo
	127.0.0.1 association.vieassoc.lo


## Apache VirtualHost configuration
After editing, your file should contain : 

	NameVirtualHost *:80
	<VirtualHost www.vieassoc.lo:80>
	    DocumentRoot "YOUR_XAMPP_LETTER:/xampp/htdocs/your_folder/public"
	</VirtualHost>
	<VirtualHost association.vieassoc.lo:80>
	    DocumentRoot "YOUR_XAMPP_LETTER:/xampp/htdocs/your_folder/public"
	</VirtualHost>

## Database deployement

1. On the command window, type : 

        php artisan migrate:install

2. Then 

        php artisan migrate


##That's it
You can try to reach your local website now : [http://www.vieassoc.lo](http://www.vieassoc.lo)

