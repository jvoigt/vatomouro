# This Component will bootstrap the pis and hook them to the local network

This is some what inspired by https://github.com/geerlingguy/raspberry-pi-dramble/tree/master/setup/networking

create your own inventory.yml with the ips for the new set up pis.

Steps:
- add host config to local .ssh/config

- generate a new "vato" user an the pi
- add "vato" to sudoers
- copy "vato" key to pi

- switch to vato user
- change ip to a static one
  - beware: on rasp3 the netinterface has a differnt name.
- add hostname


# HowTo run

you problably only need to run this ones.

cd to this dir

`ansible-playbook -i inventory.yml site.yml`

maybe the host will lose the network when netplan is applied. that is ok as it it the last step.