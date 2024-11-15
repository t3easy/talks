+++
title = "Composer"
outputs = ["Reveal"]
+++

# Composer

---

## Overview Composer

* PHP package manager
* Defines dependencies to libraries, PHP version and PHP extensions
* Generates class autoloading information
* Interacts with repositories, [Packagist.org](https://packagist.org/) is the main Composer repository

---

{{% section %}}

## Common commands

* `composer init`
* `composer create-project vendor/package:version`
* `composer install --no-dev -a` (--classmap-authoritative)

---

## Require / remove

* `composer require vendor/package:version`
* `composer require --dev vendor/package:version`

Example version constraints `@dev`, `^1.0`, `~1.1.0`

* `composer remove vendor/package`

---

## Update

* `composer update --dry-run`
* `composer update --lock`
* `composer update "vendor/package"`
* `composer update "vendor/*" --with-dependencies`
* `composer update "vendor/prefix-*" --with-all-dependencies`

---

## Show outdated packages

* `composer outdated -D -m --strict --locked`

{{% /section %}}

---

## Common Parameters

* `--dev` Require a dev package
* `--dry-run` Just show what composer would do
* `--ignore-platform-reqs` Ignores platform dependencies as PHP Version and extensions
* `--with-dependencies` Update also dependencies of packages in the argument list, except those which are root requirements.
* `--with-all-dependencies` Update also dependencies of packages in the argument list, including those which are root requirements.

---

## Further commands

* `composer why`
* `composer fund`
* `composer config minimum-stability dev`
* `composer config prefer-stable true`
* `composer show`
* `composer config gitlab-domains gitlab.my.org`
* `composer config repositories.local '{"type": "path", "url": "packages/*", "options": {"reference": "none"}}'`
* `composer bump`

---

## The composer.json and composer.lock

What *should* work vs. what is currently installed.

The composer.json defines the packages you want to install and their version range that should work.

The composer.lock *pins* the current install packages, their version and all dependencies of the packages with their version (dependency tree).

---

{{% section %}}

## Repository types

* `Composer`
* `VCS`
* `Package`
* `Path`

[More infos](https://getcomposer.org/doc/05-repositories.md)

---

## Composer repositories

* [Packagist.org](https://packagist.org/), main Composer repository, can be [disabled](https://getcomposer.org/doc/05-repositories.md#disabling-packagist-org)
* [GitLab](https://docs.gitlab.com/ee/user/packages/composer_repository/)
* [Magento](https://repo.magento.com/), Marketplace to get commercial plugins or Magento versions
* [TYPO3 ELTS](https://elts.typo3.com/), ELTS TYPO3 versions with paid subscription
* [TYPO3 TER](https://composer.typo3.org/), deprecated
* [Private Packagist](https://packagist.com/), commercial service from the company behind Composer
* [Satis](https://composer.github.io/satis/)

---

## VCS repositories

* Every Git/Subversion/Mercurial/Fossil repository can become a composer package
* Special VCS driver for Bitbucket, GitHub, GitLab (VCS, not composer repo) to use dist packages instead of the VCS repo itself if possible

---

## Package repositories

* If you want to use a project that does not support Composer through any of the means above, you still can define the package yourself by using a package repository.

---

## Path repositories

* Path to a folder containing a Composer package, repository paths can also contain wildcards like `*` and `?`.

{{% /section %}}

---

## My most used repository options

* [canonical](https://getcomposer.org/doc/articles/repository-priorities.md#making-repositories-non-canonical)  
  Should a package be searched in another repository, if it was found in the current one?
* [options.reference](https://getcomposer.org/doc/05-repositories.md#path)  
  For path repositories, how should the lock file reference packages
* `options.ssl.cafile`, trust a ca certificate during the communication with the https repository

---

## Links

* https://getcomposer.org/
* https://packagist.org/
* https://semver.madewithlove.com/

---

## Thanks for attention
