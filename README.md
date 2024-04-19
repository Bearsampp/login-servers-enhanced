[![Latest Stable Version](https://img.shields.io/packagist/v/crazy-max/login-servers-enhanced.svg?style=flat-square)](https://packagist.org/packages/crazy-max/login-servers-enhanced)
[![Minimum PHP Version](https://img.shields.io/badge/php-%3E%3D%205.6.24-8892BF.svg?style=flat-square)](https://php.net/)

# Adminer login-servers-enhanced

This plugin display a constant list of servers in login form.<br />
It's a fork of the official plugin [login-servers](https://raw.github.com/vrana/adminer/master/plugins/login-servers.php) for [Adminer](https://www.adminer.org/) with enhancements.<br />
Was created for the [Bearsampp](https://github.com/Bearsampp) project.

## Features

* Ability to select a server with different driver.

## Installation

### Adminer

Copy `plugins/login-servers-enhanced.php` in the plugins folder.

### Composer

```bash
composer require crazy-max/login-servers-enhanced
```

And download the code:

```bash
composer install # or update
```

## Getting started

Follow the instructions on the [official plugins page](https://www.adminer.org/en/plugins/).<br />
Then just add `new AdminerLoginServersEnhanced` to the `$plugins` array :

```php
function adminer_object() {
    // required to run any plugin
    include_once "./plugins/plugin.php";
    
    // autoloader
    foreach (glob("plugins/*.php") as $filename) {
        include_once "./$filename";
    }
    
    $plugins = array(
        new AdminerLoginServersEnhanced(
            array(
                new AdminerLoginServerEnhanced('127.0.0.1:3306', 'MySQL port 3306', 'server'),
                new AdminerLoginServerEnhanced('127.0.0.1:3307', 'MariaDB port 3307', 'server'),
                new AdminerLoginServerEnhanced('127.0.0.1:5432', 'PostgreSQL port 5432', 'pgsql')
            )
        )
    );
    
    /* It is possible to combine customization and plugins:
    class AdminerCustomization extends AdminerPlugin {
    }
    return new AdminerCustomization($plugins);
    */
    
    return new AdminerPlugin($plugins);
}

// include original Adminer or Adminer Editor
include "./adminer.php";
```

## How can I help?

All kinds of contributions are welcome :raised_hands:! The most basic way to show your support is to star :star2:
the project, or to raise issues :speech_balloon: You can also support this project by
[**becoming a sponsor on GitHub**](https://github.com/sponsors/crazy-max) :clap: or by making a
[Paypal donation](https://www.paypal.me/crazyws) to ensure this journey continues indefinitely! :rocket:

Thanks again for your support, it is much appreciated! :pray:

## License

Apache-2.0. See `LICENSE` for more details.
