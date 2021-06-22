docker_tuleap
=============

This role deploys Tuleap. This role is not maintained anymore.
The main repo for this role is on [Le Filament GitLab](https://sources.le-filament.com/lefilament/ansible-roles/docker_privatebin.git)

Requirements
------------

None

Role Variables
--------------

Variables from default directory :
* tuleap_url: URL for accessing Tuleap
* tuleap_db_root_pass : Root password for MySQL database
* Backups (for backups to be deployed, host needs to be in maintenance_contract group) :
  * swift parameters for 2 object storage instances where backups should be pushed daily
  * tuleap_backup_pass : Passphrase for encryption of backups


Dependencies
------------

This role requires the following Ansible collection :
* community.docker

This Docker role supposes that Traefik is deployed as an inverseproxy in front of the deployed Dockers.
The following role is used by Le Filament for deploying Traefik : docker_server (https://sources.le-filament.com/lefilament/ansible-roles/docker_server)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: docker_tuleap }
      vars:
         - { tuleap_url: "tuleap.example.org" }
         - { tuleap_db_root_pass: "veryUnsecurePassToBeModified" }

License
-------

AGPL-3

Author Information
------------------

Le Filament (https://le-filament.com)
