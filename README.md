# Vatomouro - βατόμουρο(vatómouro) = Greek for Raspberry

This is my working dir for a small kubernetes cluster running on some raspberry pis just here on my desk.

The purpose of this is more for learning, so dont expect anything interessting or new here. Feel Free to offer advise or critiscm.

## Specs of the clusters

Hardware:
- 3 Raspberry Pi 4 Mod. B
  - 8 GB RAM
  - 16 GB SD-Card
- 1 Raspberrs Pi 4 Mod. 3
  - 1 GB RAM
  - 16 GB SD-Card
- Ethernet-switch

Software:
- Ubuntu 20.10 server 64bit as host os
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

