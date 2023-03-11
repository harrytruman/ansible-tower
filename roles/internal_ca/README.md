Internal CA
=========

Add internal certificate authority to the trusted root store.

Requirements
------------

Create a directory at this level called 'files' and place your certificates within.

Role Variables
--------------

None

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: all
      roles:
         - internal-ca

License
-------

MIT
