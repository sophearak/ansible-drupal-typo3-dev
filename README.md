
##Up and running Drupal or Typo3 with no time.

This is ansible playbook for my vagrant in development.


Variable Playbook
----------------

All these varialbe you can change as you need.


Apache Virtual Host

    vhost_filename: typo3.dev.conf               #virtual host file name
    apache_vhosts:
      - server_name: typo3.dev                   #virtual host server name
        document_root: /var/www/typo3.dev        #document root

php.ini

    memory_limit: 512M
    max_execution_time: 240
    post_max_size: 10M
    upload_max_filesize: 10M

Mysql Database Authentication

    db_name: drupal
    db_user: drupal
    db_pswd: drupal

Typo3

    typo3_version: 6.2.9
    core_directory: /var/www
    site_directory: /var/www/typo3.dev

Drupal

    drupal_version: 7.34
    site_directory: /var/www/drupal.dev

Example Playbook
----------------

This is an example of play book for typo3:

    - name: install typo3 dev
      hosts: all
      sudo: yes

      roles:
        - webservers
        - databases
        - php5
        - typo3

This is an example of play book for drupal:

    - name: install typo3 dev
      hosts: all
      sudo: yes

      roles:
        - webservers
        - databases
        - php5
        - drupal


License
-------

MIT

Author Information
------------------

You can found me on twitter as [@sophearaktha][1]

[1]: https://twitter.com/sophearaktha
