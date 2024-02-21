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

## Repositories

* [Packagist.org](https://packagist.org/), main Composer repository, can be [disabled](https://getcomposer.org/doc/05-repositories.md#disabling-packagist-org)
* `Composer`  
  Vendor specific repositories, some examples
  * [GitLab](https://docs.gitlab.com/ee/user/packages/composer_repository/)
  * [Magento](https://repo.magento.com/)
  * [TYPO3 ELTS](https://elts.typo3.com/), ELTS TYPO3 versions with paid subscription
  * [TYPO3 TER](https://composer.typo3.org/), depecated
  * [Private Packagist](https://packagist.com/), commercial service from the company behind Composer
* `VCS`  
  Every Git/Subversion/Mercurial/Fossil repository can become a composer package  
  Special VCS driver for Bitbucket, GitHub, GitLab (VCS, not composer repo) to use dist packages instead of the VCS repo itselve if possible
* `Package`  
  If you want to use a project that does not support Composer through any of the means above, you still can define the package yourself by using a package repository.
* `Path`  
  Path to a folder containing a Composer package, repository paths can also contain wildcards like `*` and `?`.

[More infos](https://getcomposer.org/doc/05-repositories.md)

---

## My most used repository options

* [canonical](https://getcomposer.org/doc/articles/repository-priorities.md#making-repositories-non-canonical)  
  Should a package be searched in another repository, if it was found in the current one?
* [options.reference](https://getcomposer.org/doc/05-repositories.md#path)  
  For path repositories, how should the lock file reference to the pachage
* `options.ssl.cafile`, trust a ca certificate during the communication with the https repository

---

## Links

* https://getcomposer.org/
* https://packagist.org/
* https://npmtrends.com/vite-vs-webpack

---

## Thanks for attention