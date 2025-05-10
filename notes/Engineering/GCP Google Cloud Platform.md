---
title: "System Design"
author: "Agastya Patel"
categories: [Notes, AI, Brief]
draft: true
---
# Quick terminology
- IAM used to manage permissions

# CLI
>Installing google-cloud-sdk which allows you to control the services from cmd line
`brew install --cask google-cloud-sdk`

- gcloud cheat-sheet
# VM
- Adding ssh pub key in gcloud:
`ssh-keygen -C "username"`
create ssh pub and private key, copy the pub key to metadata in gcp and add it
- to connect vm through ssh
`ssh -i PATH_TO_PRIVATE_KEY USERNAME@EXTERNAL_IP`

### Enabling virtual display
- Installing the Chrome remote desktop on host 
  ```
  wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb
  sudo apt update
  sudo apt install ./chrome-remote-desktop_current_amd64.deb
  ```
- Install desktop env like xfce
```
sudo DEBIAN_FRONTEND=noninteractive \
apt install --assume-yes xfce4 desktop-base xfce4-terminal
```
- Follow the steps in Chrome remote desktop `setup with ssh`

### Get Mounted disks
- Get the list of the disks
`ls -l /dev/disk/by-id`
- **Format the disk** (if new):
`sudo mkfs.ext4 -m 0 -F -E lazy_itable_init=0,lazy_journal_init=0,discard /dev/sdb`
>  Replace `/dev/sdb` with your disk device name
- **Create a mount directory**:
`sudo mkdir -p /mnt/disks/disk2`
- **Mount the disk**:
`sudo mount -o discard,defaults /dev/sdb /mnt/disks/disk2`
- **Set file system permissions** (e.g., to allow all users write access):
`sudo chmod a+w /mnt/disks/disk2`