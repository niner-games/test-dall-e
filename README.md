<img src="https://github.com/akademia-slaska/base-web/blob/main/LOGO.png" alt="Logo of the Silesian Academy">
<h1 style="text-align: center">Base web app</h1>

## REQUIREMENTS

The following components are required and must be installed (if you don't already have them):

1. A local LAMP web server, e.g. [XAMPP](https://www.apachefriends.org/index.html) or standalone PHP language interpreter in version **8.0.0** at minimum
2. [Composer](http://getcomposer.org/) dependency manager
3. [Git for Windows](https://gitforwindows.org/)
4. Any web browser in a relatively new version

The solution was tested in **Windows 11 Pro** only, under the control of **PHP 8.2.4**.

## INSTALLATION

### XAMPP installation

If you don't have [XAMPP](https://www.apachefriends.org/index.html) or any other LAMP-like server, you can download and install it from the [ApacheFriends.org](https://www.apachefriends.org/download.html) website.

If you choose the 8.1 or 8.0 branch of PHP, you will need to use the `--ignore-platform-req=php` flag when executing Composer (as described below and in [here](https://forum.yiiframework.com/t/current-version-of-yii-2-not-ready-for-php-8-2/135156/2?u=trader)).

### Installing Git for Windows

If you don't have [Git for Windows](https://gitforwindows.org/) or another version of git, you can download it from their [homepage](https://gitforwindows.org/).

### Composer installation

If you do not have [Composer](http://getcomposer.org/), you can find installation instructions on the [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix) website.

### Installing the project using Git and Composer

Execute the following commands in the Windows console:

~~~
git clone git@github.com:akademia-slaska/template-repository.git
composer update --ignore-platform-req=php
~~~

The `--ignore-platform-req=php` flag must only be used if you have [PHP version 8.2 or later](https://forum.yiiframework.com/t/current-version-of-yii-2-not-ready-for-php-8-2/135156/2?u=trejder) installed.

## CONFIGURATION

### Database

Create or open the [`config/db.php`](https://github.com/akademia-slaska/base-web/blob/main/config/db.php) file and fill it with the database credentials, for example:

```php
return [
     'class' => 'yii\db\Connection',
     'dsn' => 'mysql:host=localhost;dbname=yii2basic',
     'username' => 'root',
     'password' => '1234',
     'charset' => 'utf8',
];
```

In most cases you only need to change the database name (the string after `;dbname=`), the username (`root`) in the example above, and the password (`1234` above). The rest of the file is usually left untouched.

### Migrations

Check, if any data migrations (updates) are available and run them:

~~~
cd htdocs/base-web
php yii migrate
~~~

## RUNNING

Run your local server or use the built-in PHP server:

~~~
php yii serve
~~~

Then launch your browser of choice and go to [`http://localhost:8080`](http://localhost:8080).

**Comments**:

- You have to create the database yourself if it doesn't exist; will not be created automatically
- Check and possibly change the other configuration parameters in the files located in the [`config`](https://github.com/akademia-slaska/base-web/tree/main/config) folder (if you know what you are doing; incorrect changes to these files can kill the entire application!)
- Additional information (for example about tests) can be found in the file [`YII.md`](YII.md)