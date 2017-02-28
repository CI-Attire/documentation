Install [composer](http://packagist.org) and run the following command to get the latest version:

	composer require attire/driver

Enabling this setting in `application/config/config.php` will tell CodeIgniter to look for the Composer auto-loader script.

``` php
<?php
$config['composer_autoload'] = TRUE;
```

If you have your `vendor/` directory located somewhere else, you can opt to set a specific path as well:

``` php
<?php
$config['composer_autoload'] = '/path/to/vendor/autoload.php';
```

Copy the config file inside your application config directory:

	cp path/to/vendor/attire/Driver/dist/config/attire.php application/config/

### Directory Structure

Create this directory structure inside your application:

	+-APPPATH/
	| +-themes/
	+-FCPATH
	| | +-assets/

Where:

* **APPPATH** is Codeigniter's principal directory, where all your controllers, models and views are placed.
* **FCPATH** is Codeigniter's secured installation directory, where your `index.php` file is placed (normally outside the application directory).

<!-- !!! tip
	Install this additional security components in your server (Optional).

	* [suPHP](http://www.suphp.org/Home.html) is a tool for executing PHP scripts with the permissions of their owners. -->
