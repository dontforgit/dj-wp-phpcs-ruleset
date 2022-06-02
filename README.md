# DJ WP CMS Coding Standards 

---

## Requirements

WP Engine Coding Standards (WPECS) uses [Composer](https://getcomposer.org/) to install these main dependencies:

* [PHP_Codesniffer (PHPCS)](https://github.com/squizlabs/PHP_CodeSniffer)
* [WordPress Coding Standards](https://github.com/WordPress/WordPress-Coding-Standards)

If you're using Homebrew on Mac, you can install Composer with: `brew install composer`. Otherwise, follow the 
official installation instructions for Composer.

## Installation

### Global installation

1. Clone the repository and install the dependencies:

```bash
git clone git@github.com:newscorp-ghfb/dj-wp-phpcs-ruleset.git
cd dj-wp-phpcs-ruleset
composer install
```

2. Link your coding standards to your `phpcs` installation:

```bash
phpcs --config-set installed_paths /path/to/dj-wp-phpcs-ruleset
```

### Install as a dependency

You can also install the coding standards as a dependency in your local project. Here's how

1. Add the following repository to your composer.json

```json
{
  "repositories": [
    {
      "type": "git",
      "url": "git@github.com:newscorp-ghfb/dj-wp-phpcs-ruleset.git"
    }
  ]
}
```

2. Manually add the following to `require-dev` in composer.json

```json
{
  "newscorp/dj-wp-phpcs-ruleset": "dev-master"
}
```

3. Run `composer install` or `composer update` to ensure your project is configured.

4. You can now use `DJ-WordPress-CMS` in any IDE that uses the local phpcs. If you already have a phpcs.xml in 
your project, simply add the following to it:

```xml
 <rule ref="DJ-WordPress-CMS"/>
 ```

## Usage

### Command line

Run the `phpcs` command line tool on a given file or directory, for example:

```bash
phpcs --standard=DJ-WordPress-CMS wp-load.php
```
