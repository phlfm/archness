# Files

## tar

`tar -cvz -f ARCHIVE_NAME.tar.gz file_list_to_tar`
Additional flags are `--remove-files`

`-d` to diff archive and fs

# SSH

## Generate key

`ssh-keygen -o -a 200 -t ed25519 -f ~/.ssh/ed25519 -C "john@example.com"`

-o : Save the private-key using the new OpenSSH format rather than the PEM
format. Actually, this option is implied when you specify the key type as
ed25519.

-a: number of passphrase rounds

-t: type of key to create

-C: comment

in ~/.ssh/config
```
Host example.com
  HostName 201.212.147.11
  User john
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes
```

Start the ssh-agent: `ssh-agent -s` and `ssh-add ssh_key_file`


# Images / Videos

## ffmpeg

Create gif from sequential images: `ffmpeg -f image2 -framerate 1 -i %02d.jpg -loop -1 simpson.gif`

Process video file start point `-ss hh:mm:ss` and stop after `-t hh:mm:ss`

`-o output_file_name.mp4`
`-crf NUMBER` higher = less quality
`-r NUMBER` change framerate
`-vf scale=1280:-1` change scale to 1280 horizontal and automatic vertical




# Filesystem

`df -h` list used space per mount point
`du -hs PATH` list how much space PATH occupies. `-s` is summary (total), without it, you'll get a list.

## Wipe all freespace

`sudo fstrim -v /` do a manual trim of SSD
`sync` write to disk any data in write-cache
`cat /dev/zero > ~/zeros.file` write all zeros to empty space
`cat /dev/urandom > ~/random.file` write all randoms to empty space


<br>

# System

`systemd-analyze -help` plot startup time chart and other useful stuff

`systemd-run` create single run after timelapse and other event triggered runs.

<br>

# Memory

`free -h` Display amount of free and used memory in the system

<br>

# Disk

`iotop`

## Partitions

`lsblk` shows device / partition names, size, mountpoints.
`lsblk -f` shows fstype and UUID
`fdisk`
`gdisk`

<br>

# Processor

`pstree`
`htop`


<br>

# Devices

## USB

`lsusb -t`

## PCI

`lspci -tv`
