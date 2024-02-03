# Ansible Lint

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/ansible_lint)[![Build Status](https://app.travis-ci.com/vbotka/ansible-lint.svg?branch=master)](https://app.travis-ci.com/vbotka/ansible-lint)

[Ansible role](https://galaxy.ansible.com/vbotka/ansible_lint/). Install and configure [ansible-lint](https://github.com/ansible-community/ansible-lint).

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-lint/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Supported platforms

This role has been developed and tested with
* [Ubuntu Supported Releases](http://releases.ubuntu.com/)
* [FreeBSD Supported Production Releases](https://www.freebsd.org/releases/)


## Requirements and dependencies

### Roles

- vbotka.ansible_lib

### Collections

- community.general


## Role Variables

- See default variables in *defaults/main.yml*
- See OS specific default variables in *vars/defaults/*
- See examples in *vars/main.yml.samples*
- Put OS specific custom variables into the directory *vars/*
- See the precedence of the variables in */tasks/vars.yml*


### Variables

- See *tasks/packages.yml*. The OS specific packages will be installed
  if you set

```yaml
mal_pkg_install: true
mal_pip_install: false
```

- See *tasks/pip.yml*. Instead, you can use *pip* to install
  *ansible-lint* on Linux if you set

```yaml
mal_pkg_install: false
mal_pip_install: true
```

- When installing by pip, set variable *mal_owner* to the user who
  will own the packages installed by pip

```yaml
mal_owner: admin
```

When undefined, not escalated *setup* (become=false) will gather
subset *user* and the variable *mal_owner* will be set. See
tasks/vars.yml

```yaml
mal_owner: "{{ ansible_user|default(ansible_user_id) }}"
```

The *pip* installation task will run

```yaml
become_user: "{{ mal_owner }}"
become: true
pip:
  name: ...
```

### WARNING: Do not manage system site-packages with pip

By default the pip arguments are set

```yaml
mal_pip_extraagrs: --user --upgrade
```

See [Conclusions. The pip module isn't always idempotent #28952](https://github.com/ansible/ansible/issues/28952):

  Managing system site-packages with Pip is not a good idea and will
  probably break your OS. Those should be solely managed by the OS
  package manager (apt/yum/dnf/etc.). If you want to manage env for
  some software in Python, better use a virtualenv technology.


### Download source

To download a tarball from GitHub, extract, and link it set

```yaml
mal_source_install: true
```

Optionally, set the version and clear the checksum

```yaml
mal_source_version: '6.22.0'
mal_source_checksum: ''
```

Download the archive manually, calculate, and set the checksum to
speedup repeating downloads of this version

```yaml
mal_source_version: '6.22.0'
mal_source_checksum: 'sha1:3a272ad7746edc7dd2493b695b0a0f378efbe335'
```


### Ansible lint

Use the configuration file *.ansible-lint.local* when running
*ansible-lint*. Some rules might be disabled and some warnings might
be ignored. See the notes in the configuration file.

```bash
shell> ansible-lint -c .ansible-lint.local
```


## References

- [Ansible Lint](https://docs.ansible.com/ansible-lint/)
- [Ansible Lint Default Rules](https://docs.ansible.com/ansible-lint/rules/default_rules.html#default-rules)
- [Ansible Galaxy Content Scoring](https://galaxy.ansible.com/docs/contributing/content_scoring.html#syntax-score)
- [GitHub ansible/ansible-lint](https://github.com/ansible/ansible-lint)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
