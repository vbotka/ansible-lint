Ansible Lint
============

[![Build Status](https://travis-ci.org/vbotka/ansible-lint.svg?branch=master)](https://travis-ci.org/vbotka/ansible-lint)

[Ansible role](https://galaxy.ansible.com/vbotka/ansible_lint/). Install and configure *Ansible Lint*.


Requirements
------------

None.


Role Variables
--------------

To install OS specific packages set

```
mal_packages_install: true
```

To download tarball from GitHub, extract and link it set

```
mal_source_install: true
```

Put OS specific custom variables into the directory /vars. Review /tasks/vars.yml to learn the precedence of the variables.

(TBD). Review the defaults and examples in vars.


Dependencies
------------

None.


References
----------

- [Ansible Lint](https://docs.ansible.com/ansible-lint/)
- [Ansible Lint Default Rules](https://docs.ansible.com/ansible-lint/rules/default_rules.html#default-rules)
- [Ansible Galaxy Content Scoring](https://galaxy.ansible.com/docs/contributing/content_scoring.html#syntax-score)
- [GitHub ansible/ansible-lint](https://github.com/ansible/ansible-lint)


License
-------

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)



Author Information
------------------

[Vladimir Botka](https://botka.link)
