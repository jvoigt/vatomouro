# This component describes how to setup the OS for each host

This process cannot be automatised in a secure/convenient fashion, so do it manually!!!

## Steps

- install rpi-imager 
  - `sudo apt install rpi-imager`
- flash SD-Card
- boot up
- Make the first Connection manually
  - We cannot in a secure manner login to the fresh pi and remotely set a new password. Just connect each one and set a new password by hand. sorry.
    - find the new ip address
      - see in to local router
      - or ping your networks broadcast and then `arp -na` 
      - or use nmap
    - connect via ssh with ubuntu/ubuntu
    - accept the fingerprint
    - asign a new password
    - disconnect (will happen anyway)

### Create flashed SD-Card

First we should flash an sd-Cards with ubuntu 20.10 server 
See: https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#1-overview

maybe we could use `dd` instead of rpi-imager but ...meh

## First Connection
We cannot in a secure manner login to the fresh pi and remotely and set a new password. Just connect each one and set a new password by hand. sorry.

We also have to accept the fingerprint of each pi.
Beware: if the pis get assigned a new ip by the local network (as they will use dhcp per default)  the ssh-fingerprint will not match anymore.
In this case you have to resolve that manually to.


