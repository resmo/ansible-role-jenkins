[![Build Status](https://travis-ci.org/resmo/ansible-role-jenkins.svg?branch=master)](https://travis-ci.org/resmo/ansible-role-jenkins)

Ansible Jenkins Role
====================

An Ansible role for installing and managing Jenkins CI. It can also install and update Jenkins plugins if configured.

Role Variables
--------------

* `jenkins_version`:
  - Description: Jenkins provides a stable version and a latest version of their software.
  - Values: `stable | latest`
  - Default: `stable`

* `jenkins_cli_path`:
  - Description: Path where the cli should be installed to.
  - Default: `/usr/local/lib/jenkins`

* `jenkins_cli_url`:
  - Description: URL where the cli can access the Jenkins server.
  - Default: `http://127.0.0.1:8080`

* `jenkins_user_home`:
  - Description: Path to home directory of the user running Jenkins.
  - Default: `/var/lib/jenkins`

* `jenkins_install_plugins`:
  - Description: Whether the plugins missing should be installed.
  - Values: `yes | no`
  - Default: `yes`

* `jenkins_update_plugins`:
  - Description: Whether the plugins installed and outdated should be updated.
  - Values: `yes | no`
  - Default: `yes`

* `jenkins_plugins`:
  - Description: List of plugins which should be installed (shortnames). Create a user e.g.https://jenkins.example.com/user/buildfarm/configure and copy the SSH Public Key of the Jenkins user into the web form.
  - Default: `[git, github, subversion, thinBackup, greenballs, ws-cleanup, parameterized-trigger ]`

* `jenkins_pkg_state`:
  - Description: Whether the packages should be just be installed or updated to latest.
  - Values: `installed | latest`
  - Default: `installed`

* `jenkins_service_enabled`:
  - Description: Whether the service should be started on boot or not.
  - Values: `yes | no`
  - Default: `yes`

* `jenkins_service_started`:
  - Description: Whether the service should be running.
  - Values: `started | stopped`
  - Default: `started`

Dependencies
------------

None

Example Playbook
----------------

    - hosts: jenkins-masters
      roles:
         - { role: resmo.jenkins }

License
-------

BSD

Author Information
------------------

René Moser
