## What is Composer ?
Composer is a dependency management tool in PHP

Suppose:

1. You have a project that depends on a number of libraries.
1. Some of those libraries depend on other libraries.

Composer:

1.  Enables you to declare the libraries you depend on.
1.  Finds out which versions of which packages can and need to be installed, and installs them (meaning it downloads them into your project).

## Setup in the project
To start using Composer in your project ,  all you need is a ```composer.json``` file.
## composer.json content
The first (and often only) thing you specify in composer.json is the __require__ key.<br>
You are simply telling Composer which packages your project depends on.
```
{
    "require": {
        "monolog/monolog": "1.0.*"
    }
}
```
As you see,it maps the package name to its version.<br>
The required packages will be downloaded to the project directory <br>
from the packaglist online repository: https://packagist.org/

## Getting Dependencies
To install the defined dependencies for your project,<br>
based on what is specified in composer.json file, run the install command.

```php composer.phar install ```

running the above command will download dependencies into the project<br>
it will also creates or updates a file named ``` composer.lock ``` file  into your project<br>
to maintain the proper version of dependencies among diffrent programmers of the project,
so the ``` composer.lock ``` file  should be commited into the version control.

## To update dependencies to their latest version :
```
php composer.phar update
```
