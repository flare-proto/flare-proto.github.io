---
date: 2025-10-19
categories:
    - Linux
tags:
    - Windows
---
# Returning to Windows
## Installing

- download a windows 10 iso
- flash to usb
- reboot to usb
- install windows
- let it reboot into onboarding

!!! note
    DISCONNECT FROM INTERNET NOW

- Reboot

- international or world region
- make sure to pick the no internet option
- once installed reconnect internet

## Activate(if not activated)
- run powershell

```{ .powershell .copy }
irm https://get.activated.win | iex
```

## BTRFS
- run powershell
- run:
```{ .powershell .copy } 
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
- run:
```{ .powershell .copy }
scoop bucket add nonportable
scoop install winbtrfs-np -g
```
- reboot