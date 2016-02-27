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

## Step 4) Example Usage in a controller

```php
     $sparky= $this->get("hanfrey_sparkpost.api_client");


        try {
            // Build your email and send it!
            $results = $sparky->transmission->send([
                'from'=>'From Envelope <from@sparkpostbox.com>',
                'html'=>'<html><body><h1>Congratulations, {{name}}!</h1><p>You just sent your very first mailing!</p></body></html>',
                'text'=>'Congratulations, {{name}}!! You just sent your very first mailing!',
                'substitutionData'=>['name'=>'YOUR FIRST NAME'],
                'subject'=>'First Mailing From PHP',
                'recipients'=>[
                    [
                        'address'=>[
                            'name'=>'YOUR FULL NAME',
                            'email'=>'YOUR EMAIL ADDRESS'
                        ]
                    ]
                ]
            ]);
            echo 'Woohoo! You just sent your first mailing!';
        } catch (\Exception $err) {
            echo 'Whoops! Something went wrong';
            var_dump($err);
        }
```

## Documentation

Detailed documentation on how to access each API method can be found in the documentation of the package that this bundle integrates: [Sparkpost API library](https://github.com/SparkPost/php-sparkpost/blob/master/README.md)
