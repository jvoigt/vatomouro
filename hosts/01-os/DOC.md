# Setup the OS for each host

This process cannot be automatised in a secure fashion so do it manually!!!

## Create flashed SD-Card

First we should flash an sd-Cards with ubuntu 20.10 server 
See: https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#1-overview

maybe we could use `dd` instead of rpi-imager but 

### Steps

- install rpi-imager 
  - `sudo apt install rpi-imager`
- flash SD-Card
- boot up

## Make the first Connection

We cannot in a secure manner login to the fresh pi and remotely set a new password. Just connect each one and set a new password by hand. sorry.

- find the new ip address 
  - `arp -na` 
- connect via ssh with ubuntu/ubuntu
- accept the fingerprint
- asign a new password
- disconnect (will happen anyway)
