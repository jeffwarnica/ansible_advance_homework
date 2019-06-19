db-tier
=========

Role to install and initialise Postresql

Requirements
------------

N/A

Role Variables
--------------

Varibales used are packages for the package name and database data directory:

db_tier_packages: postgresql-server
db_tier_service: postgresql.service
db_tier_dir: /var/lib/pgsql/data

Dependencies
------------

N/A

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: db-tier, db_tier_packages: postgresql-server, db_tier_service: postgresql.service, db_tier_dir: /var/lib/pgsql/data }

License
-------

BSD

Author Information
------------------

Written for the Red Hat Advanced Ansible Bootcamp
