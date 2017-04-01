## Composer

Install [composer](http://packagist.org) and run the following command to get the latest version:

	composer require attire/driver

But sure to also enable this setting in `application/config/config.php`:

```php
<?php
$config['composer_autoload'] = TRUE;
```
With this CodeIgniter can look for the Composer auto-loader script, also if you have your `vendor/` directory located somewhere else, you can opt to set a specific path as well:

```php
<?php
$config['composer_autoload'] = '/path/to/vendor/autoload.php';
```

<!-- Next, create this directory structure inside your application:

	+-APPPATH/
	| +-themes/

Where **APPPATH** is Codeigniter's principal directory, where all your controllers, models and views are placed. -->

## Defaults

Copy the config file inside your application config directory:

	cp path/to/vendor/attire/Driver/dist/config/attire.php application/config/

Finally copy the main theme inside your themes directory:

	cp path/to/vendor/attire/Driver/dist/themes/attire path/to/application/themes/

<!-- !!! tip
	Install this additional security components in your server (Optional).

	* [suPHP](http://www.suphp.org/Home.html) is a tool for executing PHP scripts with the permissions of their owners. -->
