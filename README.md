# Ansible Php5-newrelic Role

[![Build Status](https://img.shields.io/travis/weareinteractive/ansible-php5-newrelic.svg)](https://travis-ci.org/weareinteractive/ansible-php5-newrelic)
[![Galaxy](http://img.shields.io/badge/galaxy-franklinkim.php5-newrelic-blue.svg)](https://galaxy.ansible.com/list#/roles/1459)
[![GitHub Tags](https://img.shields.io/github/tag/weareinteractive/ansible-php5-newrelic.svg)](https://github.com/weareinteractive/ansible-php5-newrelic)
[![GitHub Stars](https://img.shields.io/github/stars/weareinteractive/ansible-php5-newrelic.svg)](https://github.com/weareinteractive/ansible-php5-newrelic)

> `php5-newrelic` is an [ansible](http://www.ansible.com) role which:
>
> * installs newrelic php agent
> * configures newrelic php agent
>
> Note: Tests are failing due to invalid key

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.php5-newrelic
```

Using `requirements.yml`:

```
- src: franklinkim.php5-newrelic
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-php5-newrelic.git franklinkim.php5-newrelic
```

## Dependencies

* Ansible >= 1.9
* PHP (i.e. [franklinkim.php5](https://galaxy.ansible.com/list#/roles/1401))
* Installed Newrelic server agent (i.e. [franklinkim.newrelic]())

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# newrelic_license_key: yourkey

# Sets the name of the file to send log messages to.
php5_newrelic_logfile: /var/log/newrelic/php_agent.log
# Sets the level of detail to include in the log file.
php5_newrelic_loglevel: info
# Sets the name of the file to send daemon log messages to.
php5_newrelic_daemon_logfile: /var/log/newrelic/newrelic-daemon.log
# Sets the level of detail to include in the daemon log.
php5_newrelic_daemon_loglevel: info
# Enables high security for all applications.
php5_newrelic_high_security: no
# Sets the name of the application that metrics will be reported into.
php5_newrelic_appname: myapp
```

## Example playbook

```
- hosts: all
  sudo: yes
  roles:
    - franklinkim.apt
    - franklinkim.php5-newrelic
  vars:
    apt_repositories:
      - 'ppa:ondrej/php5-oldstable'
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
    php5_newrelic_appname: "My App"
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-php5-newrelic.git
$ cd ansible-php5-newrelic
$ vagrant up
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
Copyright (c) We Are Interactive under the MIT license.
