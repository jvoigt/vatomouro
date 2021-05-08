# This componet will setup up each host as a microk8s node

More infos in the microk8s docs: https://microk8s.io/docs/install-alternatives#heading--arm

## Steps

- perpare for cgroups
  - sudo vi /boot/firmware/cmdline.txt
  - And adding the following:
        cgroup_enable=memory cgroup_memory=1
  - reboot
- install microk8s
  - check if we hab snapd
  - snap install microk8s --classic --channel=lastest/stable
- configure microk8s
    - sudo usermod -a -G microk8s $USER
    - sudo chown -f -R $USER ~/.kube
    - su - $USER
    - microk8s status --wait-ready
- install addons for microk8s
    Not shure if realy need this on all nodes.. the masternode should provide this all
  - microk8s enable dns ha-cluster ...
- Join the cluster
  - On raps4-01 
    - microk8s add-node
    - grep command
  - On new Node
    - exceute command
  - on any Node
    - check with k get node
  - maybe: drain
- create kube config so we can use kubectl from the local machine






