=====================================
vbotka.ansible_lint 2.6 Release Notes
=====================================

.. contents:: Topics


2.6.11
======

Release Summary
---------------
Feature update.

Major Changes
-------------
* tasks/packages.yml renamed to tasks/pkg.yml

Minor Changes
-------------
* Import links.yml if mal_links not empty
* Fix README tag badge.
* Use default rules in local ansible-lint


2.6.10
======

Release Summary
---------------
Feature update.

Major Changes
-------------

Minor Changes
-------------
* mal_virtualenv default not needed
* Import config.yml if mal_config not empty
* Format debug name
* Format debug mal_virtualenv_packages

Breaking Changes / Porting Guide
--------------------------------
* mal_pip_packages is a list of dictionaries
  e.g. (- name: ansible-lint, state: present)
* Add variable mal_pip_packages_state (default: present)
* mal_packages is a list of dictionaries
  e.g. (- name: ansible-lint, state: present)
* Add variable mal_packages_state (default: present)


2.6.9
=====

Release Summary
---------------
Support FreeBSD 13.3 and 14.0


2.6.8
=====

Release Summary
---------------
Enable virtual environment.

Major Changes
-------------
* Add tasks/venv.yml
* Add variables mal_virtualenv_* (mal_virtualenv: $HOME/env)
* Update tasks/sanity.yml (mal_pip_install, mal_pkg_install, and
  mal_venv_install are mutually exclusive)
* Add vars/examples
* Move tasks/packagages.yml to tasks/fn/

Minor Changes
-------------
* Remove requirements.yml from root folder (See
  github.com/ansible/ansible-lint/issues/3846)
* Update README

Breaking Changes / Porting Guide
--------------------------------
* List of packages is not backward compatible. See variable
  mal_pip_packages and mal_virtualenv_packages


2.6.7
=====

Release Summary
---------------

Major Changes
-------------

Minor Changes
-------------
* Update README
* travis.yml formatting
* Add requirements.yml (See github.com/ansible/ansible-lint/issues/3846)

2.6.6
=====

Release Summary
---------------
Formatting.


2.6.5
=====

Release Summary
---------------
Fix dependencies, tests, and Ansible lint.


2.6.4
=====

Release Summary
---------------
Fix Ansible lint.


2.6.3
=====

Release Summary
---------------
Update tests.


2.6.2
=====

Release Summary
---------------
Fix tests.


2.6.1
=====

Release Summary
---------------
Bug fixing and examples.

Major Changes
-------------

Minor Changes
-------------
* Add vars/examples

Bugfixes
--------
* Fix checksum for 6.22.1

Breaking Changes / Porting Guide
--------------------------------


2.6.0
=====

Release Summary
---------------
Ansible 2.16 update.

Major Changes
-------------
* The variable mal_packages changed to a plain list.
* Update tasks/packages.yml
* Update tasks/pip.yml; Muted pip always reporting changed in check
  mode.
* Update tasks/vars.yml; Robust defaults of mal_owner
* Update vars/defaults; Set mal_packages according mal_pip_install
* Sanity checking mal_owner and mal_pip_executable limited to
  mal_pip_install
* Add sanity check mal_pip_install and mal_pkg_install are mutually
  exclusive

Minor Changes
-------------
* Update README
* Update defaults retries/delay to 10/3
* Update debug formatting. Add new variables.

Bugfixes
--------
* Fix mal_pip_requirements is path to a pip requirements file.

Breaking Changes / Porting Guide
--------------------------------
* Change the structure of mal_packages to a plain list.
