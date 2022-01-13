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

- By default the OS specific packages will be installed

```
mal_pkg_install: true
```

- By default use *pip* to install *ansible-runner* on Ubuntu and RH

```
mal_pip_install: true
```

- Use packages, or ports to install *ansible-runner* on FreeBSD

```
mal_pip_install: false
```

- Set variable *ar_owner* to the user who will own the packages installed by pip

```
mal_owner: admin
```

By default

```
mal_owner: "{{ ansible_user_id }}"
```

The *pip* installation task will run

```
become_user: "{{ ar_owner }}"
become: true
pip:
  name: ...
```

See *tasks/packages.yml*

To download tarball from GitHub, extract and link it set

```
mal_source_install: true
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
