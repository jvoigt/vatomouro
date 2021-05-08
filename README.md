# Vatomouro - βατόμουρο(vatómouro) = Greek for Raspberry

This is my working dir for a small kubernetes cluster running on some raspberry pis just here on my desk.

The purpose of this is more for learning, so dont expect anything interessting or new here. Feel Free to offer advise or critiscm.

## Specs of the clusters

Hardware:
- 4 Raspberry Pi 4 Mod. B
  - 8 GB RAM
  - 16/64 GB SD-Card
- 1 Raspberrs Pi 3 Mod. B
  - 1 GB RAM
  - 16 GB SD-Card
- Ethernet-switch

Software:
- Ubuntu 21.04 server 64bit as host os
- ansible for managing the hosts
- mikrok8s as manager for k8s

### Network topology
As my router is an old sh*ty tincan i cannot use real subnets or anything crasy...

192.168.0.1                   the main router/Nat
192.168.0.2   - 192-168.0.9   other network appliances, like repeaters, switches, what not
192.168.0.10  - 192.168.0.60  DHCP by main router
192.168.0.100 - 192.168.0.199 metallb assing ips
192-168-0.200 - 192.168.0.229 whatever else needs a static ip
192.168.0.231 - 192.168.0.239 the vato nodes rpi3
192.168.0.241 - 192.168.0.249 the vato nodes rpi4

# Structure

This project is structured in several sub directories.

## /hosts

Contains everything related to the setup of the host nodes.
When everything is run there you should have a somewhat plain kubernetes cluster.
Most of this is written with ansible.

## /cluster

Contains everything running in the cluster.
Subdirs are representing the namespaces with in the cluster.

# Issues & learnings

## you need enough memory
Sadly the rasp3 is not strong enough. so we just can use it for test. microk8s wont run on it.

## You need enough disk space
16GB as SD Disks are not enough, when one nodes crashes the pods will move to the remaining one a and soon the diskspace will run out. 