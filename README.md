# Ansible Opencode Role

An Ansible role to install and configure Opencode (LLM interface) on various operating systems.

## Description

This role installs Opencode on the following platforms:

- **Linux (Ubuntu/Debian, including Linux Mint)**: Installed via Node.js package manager (npm)
- **Linux (Fedora, CentOS, RHEL)**: Installed via Node.js package manager (npm)
- **macOS**: Installed via Homebrew

## Requirements

### Operating Systems

- Ubuntu/Debian 18.04+
- Fedora 29+
- CentOS/RHEL 7+
- macOS 10.15+

### Ansible Version

- Ansible 2.9+

### Prerequisites

- Root/sudo privileges on target systems
- Network connectivity for package repositories

## Role Variables

### defaults/main.yml

| Variable | Default | Description |
|----------|---------|-------------|
| `admin_user` | `your_admin_user` | Administrator user for the system |
| `installation_method` | `package` | Installation method to use |
| `autoupdate` | `false` | Enable/disable automatic updates |

### vars/linux.yml

| Variable | Default | Description |
|----------|---------|-------------|
| `opencode.name` | `opencode` | Package name |
| `opencode.bin_path` | `/usr/local/bin` | Binary installation path |
| `opencode.home_dir` | `/root` | Home directory for Opencode |

## Usage

### Installing Opencode

```yaml
- hosts: all
  roles:
    - ansible-opencode
```

### Common Playbooks

There are test playbooks in the `tests/` directory you can use:

```bash
# Test on localhost
ansible-playbook -i tests/inventory tests/test.yml
```

## Testing

This role includes basic integration tests:

1. **Test Playbook**: Basic test on localhost
2. **Test Inventory**: Localhost configuration

```bash
ansible-playbook -i tests/inventory tests/test.yml
```

## License

MIT

## Author

marcelo