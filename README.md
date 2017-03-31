# Ansible Role: Fedora Copr repositories

Enable [Fedora Copr](https://copr.fedorainfracloud.org/) repository/ies and install packages from them.

## Requirements

- Ansible >= 2.2
- Fedora 25
- sudo

The role may run on other systems, but it is not tested.

## Role Variables

Repository list and packages. By default it will not install anything.

The list should be:

```yml
- name: <string>
  packages: <list>
```

```yml
copr_repo_list:
```

Keep packages update (`present | latest | absent`).

```yml
copr_repo_update: latest
```

## Example

```yml
- hosts: all
  roles:
    - ansible-role-fedora-copr
  vars:
    copr_repo_list:
      - name: ganto/lxd
        packages:
          - lxd
          - lxd-client
      - name: heikoada/terminix
        packages:
          - tilix
    copr_repo_update: latest
```

## Dependencies

None

## License

MIT

## Author Information

Apostolos Tovletoglou [ansible-role-fedora-copr](https://github.com/tovletoglou/ansible-role-fedora-copr)
