FlameCore EventObserver
=======================

[![Latest Stable](http://img.shields.io/packagist/v/flamecore/event-observer.svg)](https://packagist.org/packages/flamecore/event-observer)
[![Build Status](https://img.shields.io/travis/FlameCore/EventObserver.svg)](https://travis-ci.org/FlameCore/EventObserver)
[![Scrutinizer](http://img.shields.io/scrutinizer/g/FlameCore/EventObserver.svg)](https://scrutinizer-ci.com/g/FlameCore/EventObserver)
[![Coverage](http://img.shields.io/codeclimate/coverage/github/FlameCore/EventObserver.svg)](https://codeclimate.com/github/FlameCore/EventObserver/coverage)
[![License](http://img.shields.io/packagist/l/flamecore/event-observer.svg)](http://www.flamecore.org/projects/event-observer)

This library allows you to watch events and react to them.

Usage instructions and more information can be found [in our Wiki](https://github.com/FlameCore/EventObserver/wiki).


Getting Started
---------------

Include the vendor autoloader and use the classes:

```php
namespace Acme\MyApplication;

use FlameCore\EventObserver\Observer;
use FlameCore\EventObserver\Responder\Responder;

require_once 'vendor/autoload.php';
```

Create a new Responder object which holds the event listeners:

```php
$responder = new Responder();
$responder->setListener('action.event', function (array $data, $event) {
    print_r($data);
});
```

Create a new Observer object and give it some actions to react to:

```php
$observer = new Observer();
$observer->addResponder('action', $responder);
```

Notify the Observer of events (optionally with data):

```php
$observer->notify('action.event');
$observer->notify('action.event', ['some_data' => 123.4]);
```


Installation
------------

### Install via Composer

[Install Composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx) if you don't already have it present on your system:

    $ curl -sS https://getcomposer.org/installer | php

To install the library, run the following command and you will get the latest version:

    $ php composer.phar require flamecore/event-observer


Requirements
------------

* You must have at least PHP version 5.4 installed on your system.


Contributors
------------

If you want to contribute, please see the [CONTRIBUTING](CONTRIBUTING.md) file first.

Thanks to the contributors:

* Christian Neff (secondtruth)
