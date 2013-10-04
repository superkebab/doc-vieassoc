You will need to download first these softwares :
* A github account
* Web server like [XAMPP](http://www.apachefriends.org/fr/xampp-windows.html) (102Mb)
* Dependency Manager for PHP : [Composer](http://getcomposer.org) (600Kb)
* The last version of VieAssociative : https://github.com/serut/vieassociative
* A light and fast IDE like this one : [Sublime Text 2](http://www.sublimetext.com/2) (5Mb)


## File installation
Install the github windows software.
Then, click on tools > options and change the default storage directory by your webserver root
Fork the Vie Associative repository and clone the code on your computer.

## Database installation

Create a database with PhpMyAdmin.
Open the file web_server_root/your_vieassoc_folder/**app/config/local/database.php** and update the database password and the database name with your's local credentials

## Host file configuration
It allows you to reach the website with an other URL than localhost. You can use whathever you want, but I personnally use **.vieassoc.lo**
The file is located on YOUR_SYSTEM_LETTER:\Windows\System32\Drivers\etc and the file is **hosts** . 
On W8, you may need some tricks for editing it because it's a system file : copy paste this file anywhere else than the system's folder, edit it, and replace it where you found it.
Add this to the hosts file:
	
	127.0.0.1 www.vieassoc.lo
	127.0.0.1 association.vieassoc.lo
	127.0.0.1 doc.vieassoc.lo


## Apache VirtualHost configuration
The location of this apache file depends of your Web server. For Xampp, it's YOUR_XAMPP_FOLDER\apache\conf\extra, and you will need to edit **httpd-vhosts.conf**
After editing, your file should contain : 

	NameVirtualHost *:80
	<VirtualHost www.vieassoc.lo:80>
	    DocumentRoot "YOUR_XAMPP_LETTER:/xampp/htdocs/your_folder/public"
	</VirtualHost>
	<VirtualHost association.vieassoc.lo:80>
	    DocumentRoot "YOUR_XAMPP_LETTER:/xampp/htdocs/your_folder/public"
	</VirtualHost>

## Database deployement
Hold the SHIFT key while you right-click the Windows window. You should see "Open Command Window here"

1. On the command window, type : 

    	php artisan migrate --env=local

If you have an error when using one of these commands, please read to the next section.
## PHP not found ?

You'll have to add the directory in which the php executable is located to your "path" variable (I guess in your case that would be C:\xampp\php ). In Windows, you can do that as described [here](http://www.computerhope.com/issues/ch000549.htm)
Any directory you place in this path variable (they're separated by a semicolon) will be automatically used in, for example, a cmd shell.

##That's it
You can try to reach your local website now : [http://www.vieassoc.lo](http://www.vieassoc.lo)

