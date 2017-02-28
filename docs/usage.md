
## Loading

You can use the CI's `auto-loader` method to include Attire in your application:

``` php
<?php
$autoload['libraries'] = array('attire');
```

Or you can load it inside your controller:

``` php
<?php defined('BASEPATH') OR exit('No direct script access allowed');

class Welcome extends CI_Controller
{
	public function index()
	{
		$this->load->library('attire');
	}
}
```

Attire uses a `Twig_LoaderInterface` to locate templates, and a `Twig_Environment` to store the settings, but every aspect is controlled by his own driver.

---
## Rendering

The `render` method loads a view or a set of views passed as the first param. If you want to pass variables to that view you can set an array as the second param:

``` php
<?php
$this->attire->render('foo', ['param1' => 'value1']);
```

!!! note
    Notice that you only need to specify the view’s name without the extension `.twig`. Optionally you can set any of the available extensions (defaults: `.twig.php, .php, .php.twig`).

---
## Globals

Globals are variables witch are accessible from anywhere within a template. They’re useful when you need to have access to some data no matter which view you render. You can declare a global variable using the `addGlobal()` method:

``` php
<?php
$this->attire->addGlobal('text', new Text());
```

The variable’s name is the first param passed and their value is the second param. Next you can use it as follows:

``` html
<p>{{ text.lipsum(40) }}</p>
```

---
## Filters

Attire implements `Twig_SimpleFilter` objects to create filters. This is useful when you’re integrating new functions. Here's an example:

``` php
<?php
// Closure function
$this->attire->addFilter('rot13', function($string) {
    return str_rot13($string);
}));
// Or a simple php function
$this->attire->addFilter('rot13', 'str_rot13')
// Or a class method
$this->attire->addFilter('rot13', array('SomeClass', 'rot13Filter'));
```

The filter’s name is the first param passed and the second it’s the closure function. Now you can use it in a template:

``` html
{{ 'Twig'|rot13 }}
{# will output Gjvt #}
```

---
## Functions

Functions are defined in the exact same way as Filters, the Attire_functions driver with the add() method allows you to create new functions as follows:

``` php
<?php
$this->attire->functions->add('hello_world', function(){ return 'hello_world'; });
```

Now you can use it in a template:

``` html
<p>{{hello_world()}}</p>
<!-- prints hello_world -->
```
