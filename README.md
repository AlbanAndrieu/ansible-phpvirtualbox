# Ansible Role: PhpVirtualbox
[![Build Status](https://travis-ci.org/darthwade/ansible-role-phpvirtualbox.png)](https://travis-ci.org/darthwade/ansible-role-phpvirtualbox)
[![Gittip](http://img.shields.io/gittip/darthwade.svg)](https://www.gittip.com/darthwade/)
[![Flattr this git repo](http://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=darthwade&url=https://github.com/darthwade/ansible-role-phpvirtualbox&title=Ansible Role: PhpVirtualbox&language=&tags=github&category=software)

Ansible role that installs and configures PhpVirtualbox.

Features include:
- Installation of any PhpVirtualbox version to specified directory
- Configuration of wp-config.php
- Fetch random salts for wp-config.php (https://api.phpvirtualbox.org/secret-key/1.1/salt/)

## Installation

Using `ansible-galaxy`:
```shell
$ ansible-galaxy install darthwade.phpvirtualbox
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):
```shell
$ arm install darthwade.phpvirtualbox
```

Using `git`:
```shell
$ git clone https://github.com/darthwade/ansible-role-phpvirtualbox.git
```

## Requirements & Dependencies
- Ansible 1.4 or higher
- Curl

## Variables
Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
wp_version: 4.0
wp_install_dir: '/var/sites/awesome_phpvirtualbox_site'
wp_db_name: 'database_name_here'
wp_db_user: 'username_here'
wp_db_password: 'password_here'
wp_db_host: 'localhost'

wp_db_charset: 'utf8'
wp_db_collate: ''
wp_table_prefix: 'wp_'
wp_debug: false

wp_fs_method: 'direct'
wp_lang: ''
```

## Example playbook
```yaml
- hosts: all
  vars:
    wp_version: 4.0
    wp_install_dir: '/var/sites/awesome_phpvirtualbox_site'
    wp_db_name: 'database_name_here'
    wp_db_user: 'username_here'
    wp_db_password: 'password_here'
    wp_db_host: 'localhost'
  roles:
  - darthwade.phpvirtualbox
```

## Testing
```shell
$ git clone https://github.com/darthwade/ansible-role-phpvirtualbox.git
$ cd ansible-role-phpvirtualbox
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

Licensed under the MIT License. See the LICENSE file for details.

Copyright (c) 2014 [Vadym Petrychenko](http://petrychenko.com/)
