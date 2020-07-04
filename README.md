# Ansible Role: PHP

[![role: ubzyhd.php](https://img.shields.io/ansible/role/42673?color=blueviolet&logo=ansible&style=flat-square)](https://galaxy.ansible.com/ubzyhd/php)

![Description from Ansible](https://img.shields.io/badge/dynamic/json?label=Description&style=flat-square&query=description&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Fcontent%2F42673%2F)

[![GitHub release](https://img.shields.io/github/release/ubzyhd/ansible-role-php)](https://GitHub.com/ubzyhd/ansible-role-php/releases/) [![GitHub tag](https://img.shields.io/github/tag/ubzyhd/ansible-role-php)](https://GitHub.com/ubzyhd/ansible-role-php/tags/)

[![HitCount](http://hits.dwyl.io/ubzyhd/ansible-role-php.svg)](http://hits.dwyl.io/ubzyhd/ansible-role-php)
## Contents

- [Ansible Role: PHP](#ansible-role-php)
  - [Contents](#contents)
  - [Role Info & Build Status](#role-info--build-status)
  - [Supported OS's](#supported-oss)
  - [Role Variables](#role-variables)
  - [Example Playbook](#example-playbook)
  - [License](#license)
  - [Author Information](#author-information)
  - [Credits](#credits)

## Role Info & Build Status

|Branch             | Master | Development |
|-------------------|:--------:|:--------------:|
| Build Status:      | [![travis-ci build status](https://img.shields.io/travis/UbzyHD/ansible-role-php/master?label=build&logo=travis-ci&style=flat-square)](https://travis-ci.org/UbzyHD/ansible-role-php)       |              |
| Ansible Version: | [![https://galaxy.ansible.com/ubzyhd/php](https://img.shields.io/badge/dynamic/json?color=red&style=flat-square&label=Minimum%20Ansible%20Version%3A&query=min_ansible_version&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Fcontent%2F42673%2F)](https://galaxy.ansible.com/ubzyhd.php)       |              |
| Statistics:  | [![https://galaxy.ansible.com/ubzyhd/php](https://img.shields.io/ansible/role/d/42673?color=blue&logo=ansible&style=flat-square)](https://galaxy.ansible.com/ubzyhd.php)<br>[![https://galaxy.ansible.com/ubzyhd/php](https://img.shields.io/badge/dynamic/json?color=blue&logo=ansible&style=flat-square&label=Quality%20Score:&query=quality_score&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Fcontent%2F42673%2F)](https://galaxy.ansible.com/ubzyhd.php)<br>[![https://galaxy.ansible.com/ubzyhd/php](https://img.shields.io/badge/dynamic/json?color=blue&logo=ansible&style=flat-square&label=Content%20Score%3A&query=content_score&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Fcontent%2F42673%2F)](https://galaxy.ansible.com/ubzyhd.php)<br>[![https://galaxy.ansible.com/ubzyhd/php](https://img.shields.io/badge/dynamic/json?color=blue&logo=ansible&style=flat-square&label=Metadata%20Score%3A&query=metadata_score&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Fcontent%2F42673%2F)](https://galaxy.ansible.com/ubzyhd.php)       |              |

## Supported OS's

Debian:

- 11 - Bullseye
- 10 - Buster
- 9 - Jessie

## Role Variables

All variables for this role are listed below, along with default values located at ```defaults/main.yml```

If you do not specify a variable in your playbook then default values listed below will be used.

```yaml
php_version: "7.2"

php_modules_install:
 - php7.2-fpm
 - libapache2-mod-php7.2
 - php7.2-bz2
 - php7.2-dev
 - php7.2-apcu
 - php7.2-redis
 - php7.2-ldap
 - php7.2-common
 - php7.2-gd
 - php7.2-mysql
 - php7.2-imap
 - php7.2-cli
 - php7.2-json
 - php-imagick
 - php7.2-gmp
 - php7.2-memcached
 - php7.2-cgi
 - php7.2-curl
 - php7.2-intl
 - php7.2-pspell
 - php7.2-recode
 - php7.2-tidy
 - php7.2-xml
 - php7.2-xmlrpc
 - php7.2-xsl
 - php7.2-zip
 - php7.2-mbstring
 - php7.2-soap
 - php7.2-opcache
```

Add and remove PHP modules as neccessary depending on your needs and setup.

> Note: At the bottom of
> ```defaults/main.yml``` there is a variable lined:
> ```yaml
># DO NOT CHANGE
>ci_build_testing: false
> ```
> Do not modify this or refer to it in your playbooks as this is only used for CI/CD. You can safely ignore this.

## Example Playbook

An example playbook with all the variables can be found called ```example-playbook-php.yml```

or here:

```yaml
---
- name: UbzyHD.PHP Example Playbook
  hosts: all
  order: sorted

  gather_facts: true
  any_errors_fatal: true

  pre_tasks:

    - name: UbzyHD.PHP Example Playbook | Pinging hosts.
      action: ping

    - name: UbzyHD.PHP Example Playbook | Install Python if not already present.
      raw: test -e /usr/bin/python || (apt -y update && apt install -y python-minimal)
      changed_when: false

    - name: UbzyHD.PHP Example Playbook | Gather facts after Python is definitely present.
      setup:

  roles:
    - ubzyhd.php
```

## License

MIT

## Author Information

This role was created by Ubzy

## Credits

Jeff Geerling:

- [GitHub - geerlingguy](https://github.com/geerlingguy)
- [Website - jeffgeerling.com](https://www.jeffgeerling.com/)

>Without using his roles as the basis for mine, it wouldn't have been possible for me to create them.
