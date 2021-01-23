# This component will bootstrap the pis and hook them to the local network

Sources of inspiration:
- https://github.com/geerlingguy/raspberry-pi-dramble/tree/master/setup/networking
- https://www.linuxtechi.com/assign-static-ip-address-ubuntu-20-04-lts
- https://wiki.learnlinux.tv/index.php/Getting_Started_with_Ansible_13_-_Managing_Users

## Steps:
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

- create your own inventory.yml with the ips for the new set up pis.
  - See inventory.example.yml
  - you have to use the ip the pis have for now, probaly the ips will be asigned by dhcp see `../01-os` for more infos
- run `ansible-playbook -i inventory.yml site.yml`

maybe the host will lose the network when netplan is applied. that is ok as it it the last step.