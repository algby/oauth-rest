# Dependencies setup

In this section we are going to install the dependencies we need to build a REST API secured with oAuth.
This documentation only cover installation using [composer](https://getcomposer.org).
For more installation methods refers to each projects documentation.

## Dependencies list

* [Symfony REST edition](https://github.com/gimler/symfony-rest-edition):
    Symfony REST edition provides a symfony standart edition setup plus a bunch of bundles to build your REST API
* [FOSOAuthServerBundle](https://github.com/FriendsOfSymfony/FOSOAuthServerBundle):
    FOSOAuthServerBundle will let your application act as an oAuth server

## Composer

If you don't have Composer yet, download it following the instructions on
http://getcomposer.org or just run the following command:

    curl -s http://getcomposer.org/installer | php

## Symfony REST edition

Use composer `create-project` command to generate a new Symfony application:

    php composer.phar create-project gimler/symfony-rest-edition --stability=dev path/to/install

Composer will install Symfony and all its dependencies under the
`path/to/install` directory.

Check the [complete installation documentation](https://github.com/gimler/symfony-rest-edition) for more information

## FOSOAuthServerBundle

### Step 1: Install FOSOAuthServerBundle

Add the bundle to your `composer.json` file:

``` js
{
    "require": {
        // ...
        "friendsofsymfony/oauth-server-bundle": "<version>"
    }
}
```
Replace `<version>` by the version you want to install.
Check on [Packagist](http://packagist.org/packages/friendsofsymfony/oauth-server-bundle) to get a list of versions

Download the dependency:

    php composer.phar update

### Step 2: Enable the bundle

Finally, enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new FOS\OAuthServerBundle\FOSOAuthServerBundle(),
    );
}
```

Check the [complete installation documentation](https://github.com/FriendsOfSymfony/FOSOAuthServerBundle/blob/master/Resources/doc/index.md) for more information


Next section: [Clean up the REST Edition](02-cleanup.md)