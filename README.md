
##Up and running Drupal or Typo3 with no time.

This is ansible playbook for my vagrant in development.


Variable Playbook
----------------

All these varialbe you can change as you need.


Apache Virtual Host

    vhost_filename: drupal.dev.conf               #virtual host file name
    apache_vhosts:
      - server_name: drupal.dev                   #virtual host server name
        document_root: /var/www/drupal.dev        #document root

php.ini

    max_execution_time: 240                       
    post_max_size: 10M
    upload_max_filesize: 10M

Mysql Database Authentication
    
    db_name: drupal
    db_user: drupal
    db_pswd: drupal


    
Example Playbook
----------------

This is an example of play book for drupal:
    
    - name: install typo3 dev
      hosts: all
      sudo: yes

      roles:
        - webservers
        - databases
        - php5
        - drupal

This is an example of play book for typo3:
    
    - name: install typo3 dev
      hosts: all
      sudo: yes

      roles:
        - webservers
        - databases
        - php5
        - typo3

License
-------

MIT

Author Information
------------------

You can found me on twitter as [@sophearaktha][1]

[1]: https://twitter.com/sophearaktha
