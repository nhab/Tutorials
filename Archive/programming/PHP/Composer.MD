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
