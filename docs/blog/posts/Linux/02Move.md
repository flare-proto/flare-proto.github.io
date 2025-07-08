---
date: 2025-07-08
draft: true
categories:
    - Linux
tags:
    - de-microsofting
    - Linux
---
# Moving To Linux - Phase 1
Distro: Bazzite

Phase 1: Install and setup
<!-- more -->
!!! info "Hardware in need of software"
    - G502 Mouse - RGB, sensitivity
    - Stream deck mini

I left 166.89GB at end of disk when I installed Windows on my pc, planning for this
![alt text](ExtraSpace.png)

## Setup Problems
### Partitioning
![alt text](setupFail1.png)
/// caption
First Error Message

[Reddit Thread on this](https://www.reddit.com/r/Bazzite/comments/1f5hxhy/please_help_installation_issue_with_boot_loader/)
///

![alt text](setupFail2.png)
/// caption
If I reboot and try again

[someone's Github issue](https://github.com/ublue-os/bazzite/issues/1016)
///

what I did wrong: incorrect partitioning

my setup:
```
mount point: /boot/efi
    format:      EFI system partition
    size:        100MB

mount point:
    format: btrfs
    size: [max]

mount point: /
    format:      btrfs (subvolume)
```
!!! info "Correct Partitioning"
    ```
    mount point: /boot/efi
        format:      EFI system partition
        size:        300MB

    mount point: /boot
        format:      ext4
        size:        1GB

    mount point:
        format: btrfs
        size: [max]

    mount point: /
        format:      btrfs (subvolume)

    mount point: /var
        format:      btrfs (subvolume)

    mount point: /var/home
        format:      btrfs (subvolume)
    ```