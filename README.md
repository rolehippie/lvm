# lvm

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/lvm/status.svg)](https://cloud.drone.io/rolehippie/lvm)

Ansible role to configure lvm

## Table of content

* [Default Variables](#default-variables)
  * [lvm_volumes](#lvm_volumes)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### lvm_volumes

List of volumes to manage

#### Default value

```YAML
lvm_volumes: []
```

#### Example usage

```YAML
lvm_volumes
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

None.

## License

Apache-2.0

## Author

Thomas Boerger
