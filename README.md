# MicroEncode
micro package for php containing encoding utility libraries

## Installation
use composer to add **MicroEncode** to your PHP project:
```
composer require katmore/micro-encode
```

## Usage
 * [Encoding data to XML](#usage---xmlencoder)
 * [Encoding data to HTML](#usage---htmlencoder)

### Usage - XmlEncoder
The [`XMLEncoder`](./src/MicroEncode/XmlEncoder.php) class facilitates serializing data into an XML document. The [PHP data types](http://php.net/manual/en/language.types.intro.php) supported are: [`boolean`](http://php.net/manual/en/language.types.boolean.php), [`integer`](http://php.net/manual/en/language.types.integer.php), [`float`](http://php.net/manual/en/language.types.float.php), [`string`](http://php.net/manual/en/language.types.string.php), [`array`](http://php.net/manual/en/language.types.array.php), [`object`](http://php.net/manual/en/language.types.object.php), and [`null`](http://php.net/manual/en/language.types.null.php). The serialized XML adheres to the [Flat XML Schema](https://github.com/katmore/flat/wiki/xmlns) specification.

The following is an example of encoding an associative array to XML:
```php
<?php
use MicroEncode\XmlEncoder;
require __DIR__.'/vendor/autoload.php';

$myData = [
   'my'=>'data'
];

echo (new XmlEncoder($myData));
```
The above code should output the following XML:
```html
<?xml version="1.0" encoding="UTF-8"?>
<fx:data fx:created="2018-05-30T15:32:18-07:00" fx:md5="37a6259cc0c1dae299a7866489dff0bd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:extxs="https://github.com/katmore/flat/wiki/xmlns-extxs" fx:flat-xml-ver="0.2" xmlns:fx="https://github.com/katmore/flat/wiki/xmlns" xmlns="https://github.com/katmore/flat/wiki/xmlns-object" xsi:type="extxs:Hashmap">
   <my xsi:type="xs:string">data</my>
</fx:data>
```

### Usage - HtmlEncoder
The [`HtmlEncoder`](./src/MicroEncode/HtmlEncoder.php) class facilitates serializing data into an XML document. The [PHP data types](http://php.net/manual/en/language.types.intro.php) supported are: [`boolean`](http://php.net/manual/en/language.types.boolean.php), [`integer`](http://php.net/manual/en/language.types.integer.php), [`float`](http://php.net/manual/en/language.types.float.php), [`string`](http://php.net/manual/en/language.types.string.php), [`array`](http://php.net/manual/en/language.types.array.php), [`object`](http://php.net/manual/en/language.types.object.php), and [`null`](http://php.net/manual/en/language.types.null.php).

The following is an example of encoding an associative array to HTML:
```php
<?php
use MicroEncode\HtmlEncoder;
require __DIR__.'/vendor/autoload.php';

$myData = [
   'my'=>'data'
];

echo (new HtmlEncoder($myData));
```
The above code should output the following HTML:
```html
<ul data-type="array">
   <li data-index="0" data-key="my" data-role="item"><span data-role="item-key">my</span>:&nbsp;<span data-role="item-value" data-type="string">data</span></li><!--/data-item: (my)-->
</ul>
```

## Legal
### Copyright
MicroEncode - https://github.com/katmore/micro-encode

Copyright (c) 2012-2018 Doug Bird. All Rights Reserved.

### License
MicroEncode is copyrighted free software.
You may redistribute and modify it under either the terms and conditions of the
"The MIT License (MIT)"; or the terms and conditions of the "GPL v3 License".
See [LICENSE](https://github.com/katmore/micro-encode/blob/master/LICENSE) and [GPLv3](https://github.com/katmore/micro-encode/blob/master/GPLv3).
