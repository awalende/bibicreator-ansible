Role Name
=========

This Role installs the linux image creator tool BibiCreator for usage in the denBI Cloud Project (https://www.denbi.de/).
BibiCreator is a web framework, for simple image creation and image deployment on OpenStack Clouds by using Ansible and Packer.

Requirements
------------

1. Internet Connection on the host.
2. Valid OpenStack connection and credentials.
3. MySQL Database (can be installed by this role, see Role Variables for more info).

Role Variables
--------------
vars/main.yaml

| Variable		| Default		| Description			|
| ------------- |:-------------:| ---------------------:|
| bibicreator_path | "/home/{{ ansible_user_id }}/bibicreator" | The path on where bibicreator will be installed |



Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
