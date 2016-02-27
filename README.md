# sparkpost-bundle [![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/Hanfrey/sparkpost-bundle/blob/master/LICENSE)

Bundle for using Sparkpost in symfony
# Installation

## Step 1) Get the bundle

 

    composer require hanfrey/sparkpost-bundle


## Step 2) Register the bundle

To start using the bundle, register it in your Kernel.

``` php
<?php
// app/AppKernel.php
public function registerBundles()
{
    $bundles = array(
        // ...
        new Hanfrey\SparkpostBundle\HanfreySparkpostBundle(),
        // ...
    );
}
```

## Step 3) Configure the default API token to use (mandatory)


Here is an example:
```yaml
# app/config/config.yml
hanfrey_sparkpost:
    api_token: 1212334ba # replace with your own
```


## Documentation

Detailed documentation on how to access each API method can be found in the documentation of the package that this bundle integrates: [Sparkpost API library](https://github.com/SparkPost/php-sparkpost/blob/master/README.md)
