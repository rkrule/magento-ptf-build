[![Radial Logo](assets/radial_logo.png)](http://www.radial.com/)

# Radial Magento Payments Tax Fraud Extension


## Installation

> The Radial Payments, Tax, and Fraud (PTF) extension is installed with [Composer](https://getcomposer.org/) and deployed to your Magento project directory with [Magento Composer Installer](https://github.com/Cotya/magento-composer-installer).

> To install the last stable release copy the [composer.json](composer.json) file into the **base Magento installation directory** - it is strongly recommended to do this in a non-production environment, test the results, and then use a tagged file repository to make it live. The file may be curl'ed to the server via:

`curl https://raw.githubusercontent.com/RadialCorp/magento-ptf-build/master/composer.json -o composer.json`

> Now run the following command:

`composer install`

> The output should look something like this:

<pre>
./composer.json has been created
Loading composer repositories with package information
Updating dependencies (including require-dev)
  - Installing psr/log (1.0.0)
    Loading from cache

  - Installing symfony/polyfill-mbstring (v1.1.1)
    Loading from cache

  - Installing symfony/console (v2.8.5)
    Loading from cache

... more output ...

Writing lock file
Generating autoload files
please define your magento root dir [root]
Autoloader patch to root/app/Mage.php was applied successfully
</pre>

> You will be prompted to define your Magento root, you should provide the root of your Magento installation.

> Why composer-based installation?  The Radial PTF extension leverages a number of open-source extensions to accomplish its goal, you can see them listed out in the composer output or later in your composer.lock file.  Composer is the easiest way to ensure that an installation of Magento contains all these dependencies for Radial PTF to function correctly.  

## Upgrading Radial Extensions

Upgrades to Radial Extensions is also done via composer to help ensure that *all* upgrade dependencies are accounted for.  The recommended way to take an update is to grab the latest released version of composer.json (latest released is always what is on Master of this repository) and then run composer update:

<pre>
curl https://raw.githubusercontent.com/RadialCorp/magento-ptf-build/master/composer.json -o composer.json

composer.phar update
you may want to add the packages.magento.com repository to composer.
add it with: composer.phar config -g repositories.magento composer https?://packages.magento.com
Loading composer repositories with package information
Updating dependencies (including require-dev)
  - Installing radial/magento-payments-transactions (1.0.3)
    Downloading: 100%

  - Removing radial/magento-payments-creditcard (1.0.0)
  - Installing radial/magento-payments-creditcard (1.0.1)
    Downloading: 100%

Package videlalvaro/php-amqplib is abandoned, you should avoid using it. Use php-amqplib/php-amqplib instead.
Writing lock file
Generating autoload files
/var/www/magento/app/Mage.php was already patched
</pre>

Manual updates to composer.json may be possible, but should be done in conjunction with instructions from Radial engineering staff.

Always remember to cache clear and check for updates to app/etc/rom.xml.sample when updating!

## Next Docs

[Main](../README.md)

[Setup and Configuration](SETUP.md)

[Integrators Guide](SI.md)

[Troubleshooting](SUPPORT.md)
