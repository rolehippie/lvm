# lvm

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/lvm) [![Testing Build](https://github.com/rolehippie/lvm/workflows/testing/badge.svg)](https://github.com/rolehippie/lvm/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/lvm/workflows/readme/badge.svg)](https://github.com/rolehippie/lvm/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/lvm/workflows/galaxy/badge.svg)](https://github.com/rolehippie/lvm/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/lvm)](https://github.com/rolehippie/lvm/blob/master/LICENSE)

Ansible role to install and configure the logical volume manager.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Default Variables](#default-variables)
  - [lvm_group_volumes](#lvm_group_volumes)
  - [lvm_host_volumes](#lvm_host_volumes)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### lvm_group_volumes

List of volumes to manage per group

#### Default value

```YAML
lvm_group_volumes: '{{ lvm_volumes | default([]) }}'
```

#### Example usage

```YAML
lvm_group_volumes:
  - name: lv_data
    group: vg_data
    disks:
      - /dev/sda
    fstype: xfs
    size: 100g
    resizefs: True
    mountpoint: /mnt/data
    mountopts:
      - ro
      - noauto
    state: present
```

### lvm_host_volumes

List of volumes to manage per host

#### Default value

```YAML
lvm_host_volumes: []
```

#### Example usage

```YAML
lvm_host_volumes:
  - name: lv_data
    group: vg_data
    disks:
      - /dev/sda
    fstype: xfs
    size: 100g
    resizefs: True
    mountpoint: /mnt/data
    mountopts:
      - ro
      - noauto
    state: present
```

## Discovered Tags

**_lvm_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
