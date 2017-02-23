## Composer

Install [composer](http://packagist.org) and run the following command to get the latest version:

	composer require attire/driver

Enabling this setting in `application/config/config.php` will tell CodeIgniter to look for the Composer auto-loader script.

``` php
<?php
$config['composer_autoload'] = TRUE;
```

If you have your `vendor/` directory located somewhere else, you can opt to set a specific path as well:

<!-- {% highlight php startinline %}
<?php
$config['composer_autoload'] = '/path/to/vendor/autoload.php';
?>{% endhighlight %} -->

### Directory Structure

Create this directory structure inside your application:

	+-APPPATH/
	| +-themes/
	+-FCPATH
	| | +-assets/

Where:

* **APPPATH** is Codeigniter's principal directory, where all your controllers, models and views are placed.
* **FCPATH** is Codeigniter's secured installation directory, where your `index.php` file is placed (normally outside the application directory).

### Assets permissions

Set the assets directory with writable permissions.

	sudo chmod 0777 assets/

### Config File

Copy `dist/config/attire.php` file inside your config directory:

	+-APPPATH/
	| +-config/
	| | +-attire.php
