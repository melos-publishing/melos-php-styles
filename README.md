# melos-php-styles
PHPCS Fix Lib

# Installation

Best installed by hand, insert 2 lines into your `composer.json`:

1. In the "repositories" section:
`{"type": "vcs", "url": "https://github.com/melos-publishing/melos-php-styles"},`

2. In the "require-dev" section:
`"melos/php-styles": "dev-master",`

Run `composer update --no-scripts`

Your *bin* directory will now have a `php-cs-fixer` command. This will either be in `bin/php-cs-fixer`
or `vendor/bin/php-cs-fixer`

## Test it works:

`bin/php-cs-fixer fix --dry-run`
or
`vendor/bin/php-cs-fixer fix --dry-run`

In your root project dir you will now have a file called `.php_cs.dist`

Open this file in your IDE and modify it to:
```
<?php

$finder = PhpCsFixer\Finder::create()
  ->in([
    __DIR__.'/src',
    __DIR__.'/tests',
  ]);

return Melos\styles($finder);
```

This is a typical config for one of our v2 projects. If you want to fix more directories, just add them to the array.

## Run it

This will modify your PHP files!

`bin/php-cs-fixer fix`
or
`vendor/bin/php-cs-fixer fix`
