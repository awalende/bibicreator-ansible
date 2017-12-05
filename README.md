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
All of them are required.

| Variable		| Default		| Description			|
| ------------- |:-------------:| ---------------------:|
| bibicreator_path | "/home/{{ ansible_user_id }}/bibicreator" | The path on where bibicreator will be installed |
| install_mysql | 'yes' | Also installs mysql and automatically creates user and database |
| install_apache2 | 'yes' | Also installs apache2 with mod_wsgi and ssl certificates |

The followig variables are for the bibicreator config file which will be placed in /etc/bibicreator/config.ini
After changes, you'll need to restart the application (or the apache webserver).

| Variable		| Default		| Description			|
| ------------- |:-------------:| ---------------------:|
| mysql_user | bibicreator | The mysql database user for BibiCreator |
| mysql_password | password | The mysql database password |
| db_url | localhost | The path to the mysql database |
| os_auth_url | OSAUTHURL | The url to the OpenStack authentication endpoint |
| os_user | OPENSTACKUSER | The OpenStack-Account username |
| os_password | OSPASSWORD | The OpenStack-Account password |
| os_project_name | bibiserv | The standard project on which new images will be placed in OpenStack |
| os_user_domain_id | default | The standard OpenStack user domain |
| os_project_domain_name | default | The standard OpenStack project domain name |
| os_base_img_id | 5dc6a020-cfb9-4cb3-b70e-d2967772a1c0 | The base image on OpenStack which will be used for new builds |
| os_flavor | BiBiGrid Debug | The favor used in a build process |
| os_ssh_username | ubuntu | The standard ssh username for packer and ansible |
| os_network | b9f8e25f-98ca-4e22-9c1e-152d9aca5aa5 | The OpenStack network id for instances created by the build process |
| os_availability_zone | default | On which zone will the build process be executed? |
| admin_password | password | Create the admin account on first startup with this password. |
| admin_email | admin@email.de | The email for the administrator. |



Dependencies
------------

No dependencies.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - bibicreator-ansible

Don't run this script as administrator if you want to use it witch Apache2, hence it is not able to display webpages created by root.
After install, the webpage is accessable under https://localhost
HTTP alone is not supported/allowed.

License
-------

BSD

Author Information
------------------

B.Sc. Alex Walender
AG Computational Metagenomics
CeBiTec
awalende@cebitec.uni-bielefeld.de
