# Slim Framework Command Line
This repository contains a set of useful command lines for slim application. It uses the [symfony console component](https://symfony.com/doc/current/components/console.html).

## Install

Via composer

``` bash
$ composer require candrianarijaona/slim-command
```

Requires Slim 3.0.0 or newer.

## Usage

First, you need to create a PHP script to define the console application.
In this case, let's put it under the directory /bin.
Make you sure that your console has an access to your slim app.

```php
#!/usr/bin/env php
<?php

require __DIR__.'/../index.php'; //Path to your public index.php

use Symfony\Component\Console\Application;

$application = new Application();
$container = $app->getContainer();

// ... register commands

$application->run();
```

You can register additionnal command using add().

## Available commands

* [Route](#route)
* [Container](#container)

### Router

```php
<?php
use Candrianarijaona\Command\Router\DebugRouterCommand;

$application->add(new DebugRouterCommand($container->router));
```

Executing the commmand:

```bash
php bin/console debug:router
```

### Container

```php
<?php
use Candrianarijaona\Command\Container\DebugContainerCommand;

$application->add(new DebugContainerCommand($container->router));
```

Executing the commmand:

```bash
php bin/console debug:container
```
