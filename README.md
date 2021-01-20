# ansible-mdadm


An [Ansible] role to install and manage [mdadm] raid arrays.

## Requirements

- Available unpartitioned disk devices

## Role Variables

```
---
# defaults file for ansible-mdadm
#
# Define Raid Arrays to manage
mdadm_arrays:
    # Define array name
  - name: 'md0'
    # Define disk devices to assign to array
    devices:
      - '/dev/sdb'
      - '/dev/sdc'
    # Define filesystem to partition array with (optional)
    # ext4|ext3|ext2|btrfs|vfat|lvm|xfs
    filesystem: 'ext4'
    filesystem_opts: ''
    # Define the array raid level
    # 0|1|4|5|6|10
    level: '1'
    # Define mountpoint for array device (optional)
    mountpoint: '/mnt/md0'
    # Define if array should be present or absent
    state: 'present'
    # Set mount options (optional)
    opts: 'noatime'
  # - name: 'md0'
  #   devices:
  #     - '/dev/sdb'
  #     - '/dev/sdc'
  #     - '/dev/sdd'
  #   filesystem: 'ext4'
  #   level: '5'
  #   mountpoint: '/mnt/md0'
  #   state: 'present'
```

## Dependencies

None

## Install

clone git into /etc/ansible/roles/ansible-mdadm


## Playbook

```

---
- hosts: localhost
  become: true
  vars:
  roles:
    - role: ansible-mdadm
  tasks:

```


