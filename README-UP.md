# Up

Lighter-than-air systems automation, inspired by Ansible.

## Why?

Ansible is a fantastic tool, but has one minor flaw that is perhaps
unreasonably frustrating in certain scenarios: it requires a full Python
environment.

For instance, if you need to quickly configure a container or virtual
machine but ensure development and automation tools won't stick around in
the final version, Ansible becomes overly complex. As a self-contained
binary, Up is easier to install and remove cleanly.

Up also inherits performance improvements and added security benefits from
being written in a systems language like Rust.

## Security

Because Up operates in a security sensitive environment, please notify
<sec@secretfader.com> before filing publicly-visible issues related to
framework security.

As of the latest release, Up only installs and configures existing
packages and isn't responsible for vulnerabilities found in code retrieved
from operating system package registries.

## Terminology

**Plan**

An overarching configuration proposal, which contains multiple roles that
will be applied to selected hosts. For example, a group of roles may be
gathered and executed in order to prepare a system, like installing and
configuring tools to faciliate software development.

**Role**

A list of tasks that are required to accomplish a specific goal. For
example: installing Neovim, a code editor.

**Task**

Processes(s) that will be executed in order to fulfill a Role, including
checks that may need to be completed along the way. Examples include
checking if a command exists, enabling a repository, or installing
a package.

## Examples

```yaml
- name: Install and upgrade base packages
  roles:
    - install-packages
    - upgrade-packages
```

## Goals

* Ansible-inspired syntax for systems automation
* Reliable, single-binary installation (for `x86_64` and ARM
  architectures)

## Anti-Goals

* Full Ansible compatibility

## License

Copyright 2020 Nicholas Young. Released under the [3-Clause BSD
License](LICENSE).
