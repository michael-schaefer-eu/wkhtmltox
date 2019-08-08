# wkhtmltox

This repository contains the [latest stable compiled binaries](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/latest) of wkhtmltopdf and wkhtmltoimage from the [wkhtmltopdf project](https://github.com/wkhtmltopdf/wkhtmltopdf).

The binaries are built for Ubuntu 18.04 bionic, amd64 and i386 architectures are included.

## Why
Because apt package is outdated.
```bash
$ sudo apt install wkhtmltopdf
```
will install wkhtmltopdf version 0.12.4

When it's not possible to install the latest version via .deb package with apt
```bash
wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb
sudo apt install ./wkhtmltox_0.12.5-1.bionic_amd64.deb
```

Or sometimes you just want a quick solution for your dev environment ;)

## Installation

This package is published on [Packagist](https://packagist.org/packages/michael-schaefer-eu/wkhtmltox) and should be installed with [Composer](https://getcomposer.org/download/).

The version of the binary is equal to the git tag.
Composer will install the latest version by default.
```bash
$ composer require-dev michael-schaefer-eu/wkhtmltox
```
_Note: you should not use this package (or any other of that kind) in production environments!_


Composer will install the package in your project path into the _vendor/michael-schaefer-eu/wkhtmltox/_ directory.

The binaries are located in the _vendor/michael-schaefer-eu/wkhtmltox/bin/_ directory.

Composer will symlink them to the _vendor/bin/_ directory.

_Optional:_ You can also symlink them to the _/usr/local/bin/_ directory, as apt would install normally there.

```bash
$ ln -s /absolute/path/to/your/project/vendor/michael-schaefer-eu/wkhtmltox/bin/wkhtmltopdf-bionic-amd64 /usr/local/bin/wkhtmltopdf
$ ln -s /absolute/path/to/your/project/vendor/michael-schaefer-eu/wkhtmltox/bin/wkhtmltoimage-bionic-amd64 /usr/local/bin/wkhtmltoimage
```

Check the Version:
```bash
$ wkhtmltopdf -V
wkhtmltopdf 0.12.5 (with patched qt)
```

### Usage

With the [KNP-Snappy](https://github.com/KnpLabs/snappy) package, you can now use the binaries to create PDFs or Images from HTML.

You can use the path constants from this project to easily locate the binary paths (with PSR 4 Autoloader):

``` php
<?php
use Knp\Snappy\Pdf;
use Knp\Snappy\Image;
use Wkhtmltox\Wkhtmltopdf;
use Wkhtmltox\Wkhtmltoimage;

$snappyPdf = new Pdf(Wkhtmltopdf::BIONICAMD64);
$snappyImage = new Image(Wkhtmltoimage::BIONICAMD64)
``` 

_OR_ If you symlinked the binaries to _/usr/local/bin_:

``` php
<?php
use Knp\Snappy\Pdf;
use Knp\Snappy\Image;

$snappyPdf = new Pdf('/usr/local/bin/wkhtmltopdf');
$snappyImage = new Image('/usr/local/bin/wkhtmltoimage');
```

### License

This package is published under the same GNU General Public License v3.0 [LICENSE](https://github.com/michael-schaefer-eu/wkhtmltox/blob/master/LICENSE) as the [wkhtmltopdf project](https://github.com/wkhtmltopdf/wkhtmltopdf).
