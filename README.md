# Creating your first Composer/Packagist package

Directory & Files Structure
----------------------------

```
hello-world (root dir)
  |- src
    |- HelloWorld
      |- SayHello.php
```

Our `SayHello.php` file will have:

``` ruby
<?php 

namespace HelloWorld;

class SayHello
{
    public static function world()
    {
        return 'Hello World, Composer!';
    }
}
```
Starting Composer
----------------
```
$ composer init
Package name (<vendor>/<name>) [smithfoto/hello-world]: <your-vendor>/hello-world
Description []: My first Composer project
Author [Sunnguon TAING <taingsunnguon@gmail.com>]: Your Name <your@name.com>
Minimum Stability []: dev
Would you like to define your dependencies (require) interactively [yes]? no
Would you like to define your dev dependencies (require-dev) interactively [yes]? no
```
``` ruby
{
    "name": "<your-vendor>/hello-world",
    "description": "My first Composer project",
    "authors": [
        {
            "name": "Your Name",
            "email": "your@name.com"
        }
    ],
    "minimum-stability": "dev",
    "require": {}
}
```
`Do you confirm generation [yes]? yes`

Now you have "composer.json" file saved in your root dir. It's almost ready but we must do some changes: 

``` ruby
{
    "name": "<your-vendor>/hello-world",
    "description": "My first Composer project",
    "authors": [
        {
            "name": "Your Name",
            "email": "your@name.com"
        }
    ],
    "minimum-stability": "dev",
    "require": {
        "php": ">=5.5.0"
    },
    "autoload": {
        "psr-0": {
            "HelloWorld": "src/"
        }
    }
}
```
Testing Package
--------------
Shure we want to do a simple test to verify if our class is working well. You can create a new project and "paste" your classes inside it or test inside your own project, wich is better and easier. We're creating a Composer project so we must have Composer files installed inside our projects. So, install it running "composer install" inside your root dir:
`composer install`

