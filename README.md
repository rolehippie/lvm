# lvm

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/lvm) [![Build Status](https://img.shields.io/drone/build/rolehippie/lvm/master?logo=drone)](https://cloud.drone.io/rolehippie/lvm) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/lvm)](https://github.com/rolehippie/lvm/blob/master/LICENSE) 

Ansible role to install and configure the logical volume manager. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [lvm_group_volumes](#lvm_group_volumes)
  * [lvm_host_volumes](#lvm_host_volumes)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

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

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
