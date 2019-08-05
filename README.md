# wkhtmltox

This repository contains the static compiled binaries from the [wkhtmltopdf project](http://wkhtmltopdf.org/).

It contains the [latest stable release](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/latest) of wkhtmltopdf and wkhtmltoimage compiled for Ubuntu 18.04 bionic, amd64 and i386 architectures.

## Installation

The version of the binary is equal to the git tag.
To install the latest version, use '0.12.5'.

### Usage

You can use the path constants to easily locate the binary with PSR 4 Autoloader: 

``` php
$pathToAmd64 = \Wkhtmltox\Wkhtmltopdf::BIONIC-AMD64;
```

To get the real path of binary:

``` php
$pathToAmd64 = realpath(\Wkhtmltox\Wkhtmltopdf::BIONIC-AMD64);
```

