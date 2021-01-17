# This Component will bootstrap the pis and hook them to the local network

This is some what inspired by https://github.com/geerlingguy/raspberry-pi-dramble/tree/master/setup/networking

create your own inventory.yml with the ips for the new set up pis.

Steps:

- copy "vato" key to pi
- generate a new "vato" user an the pi
- add "vato" to sudoers

- switch to vato user
- change ip to a static one
- add hostname
- add host config to local .ssh/config