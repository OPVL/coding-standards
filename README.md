# Coding Standards

A standard set of linting rules for PHP projects.

## Installation

Add our composer repository to your `composer.json`:

```json
    ...
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/opvl/coding-standards"
        }
    ]
    ...
```

You can then install the package via composer:

```bash
$ composer require opvl/coding-standards --dev
```


## Standard composer scripts

Below are the script we recommend you add to your `composer.json` to simplify working with these tools.

```
"scripts": {
  "php-lint": "vendor/bin/parallel-lint --exclude vendor --exclude node_modules --exclude sdk/vendor .",
  "phpcs": "vendor/bin/phpcs YOUR_DIRECTORIES --standard=./vendor/opvl/coding-standards/phpcs.xml",
  "doc-check": "vendor/bin/php-doc-check YOUR_DIRECTORIES",
  "lint": [
    "@composer php-lint",
    "@composer phpcs",
    "@composer doc-check",
  ],
  "cbf": "vendor/bin/phpcbf YOUR_DIRECTORIES --standard=./vendor/opvl/coding-standards/phpcs.xml",
}
```
