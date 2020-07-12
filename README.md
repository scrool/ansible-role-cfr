# Ansible Role: `cfr`

Installs or uninstalls [CFR](http://www.benf.org/other/cfr/) - another java
decompiler - from Maven Central. Creates or removes a wrapper to start the
program from the shell.

## Requirements

- A recent version of Ansible. Tested on 2.9. It might work on previous versions.
- Fedora 31. It might work on other versions.
- Access to a Maven Central over the internet.
- CFR requires a supported version of a Java Runtime and Development Kit on
  the PATH to run. Role does not install it. For detailed information see [CFR
  FAQ](http://www.benf.org/other/cfr/faq.html).

## Role Variables

All variables which can be overridden are stored in
[defaults/main.yml](defaults/main.yml) file and listed in a table bellow as
well.

| Name              | Default Value | Description  |
| ----------------- | ------------- | ------------ |
| `cfr_state`       | present       | By default installs the program. Set to "absent" to uninstall. |
| `cfr_version`     | latest        | Version that will be installed. By default "latest". |
| `cfr_install_dir` | /opt/cfr      | Directory to which program will be installed. |

## Example Playbook

### Install

To install latest version of the program:

```yaml
- hosts: all
  roles:
    - role: scrool.cfr
```

### Uninstall

To uninstall set state variable to "absent":

```yaml
- hosts: all
  roles:
    - role: scrool.cfr
      vars:
        cfr_state: absent
```

## License

This project is licensed under MIT License. See [LICENSE](LICENSE) for more
details.

See [CFR - License](http://www.benf.org/other/cfr/license.html) for license
information of CFR.

## Author Information

- [Pavol Babinčák](https://github.com/scrool)
