# Ansible Role: WordPress

Ansible role that installs and configures WordPress.

Features include:
- Installation of any WordPress version to specified directory
- Configuration of wp-config.php
- Fetch random salts for wp-config.php (https://api.wordpress.org/secret-key/1.1/salt/)

Forked from: darthwade/ansible-role-wordpress

## Installation

Using `ansible-galaxy`:
```shell 
$ ansible-galaxy install darthwade.wordpress
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):
```shell 
$ arm install darthwade.wordpress
```

Using `git`:
```shell 
$ git clone https://github.com/alanlok/ansible-role-wordpress.git
```

## Requirements & Dependencies
- Ansible 1.4 or higher
- Curl

## Variables
Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml 
wp_version: 4.0
wp_install_dir: '/var/sites/awesome_wordpress_site'
wp_db_name: 'database_name_here'
wp_db_user: 'username_here'
wp_db_password: 'password_here'
wp_db_host: 'localhost'

wp_db_charset: 'utf8'
wp_db_collate: ''
wp_table_prefix: 'wp_'
wp_debug: false

apache_user: 'www-data'
apache_group: 'www-data'

wp_fs_method: 'direct'
wp_lang: ''
```

## Example playbook
```yaml
- hosts: all
  vars:
    wp_version: 4.0
    wp_install_dir: '/var/sites/awesome_wordpress_site'
    wp_db_name: 'database_name_here'
    wp_db_user: 'username_here'
    wp_db_password: 'password_here'
    wp_db_host: 'localhost'
  roles:
  - darthwade.wordpress
```

## Testing
```shell 
$ git clone https://github.com/darthwade/ansible-role-wordpress.git
$ cd ansible-role-wordpress
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
