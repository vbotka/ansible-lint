=====================================
vbotka.ansible_lint 2.6 Release Notes
=====================================

.. contents:: Topics


2.6.8
=====

Release Summary
---------------

Major Changes
-------------

Minor Changes
-------------
* Remove requirements.yml from root folder (See
  github.com/ansible/ansible-lint/issues/3846)


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
Fix dpendencies, tests, and Ansible lint.


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
Bugfixing and examples.

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
