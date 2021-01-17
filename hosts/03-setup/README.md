# Setup up each Node Host

TODO:

- update userpassword
- ip static ip
- set hostname
- perpare for cgroups
  - sudo vi /boot/firmware/cmdline.txt
  - And adding the following:
        cgroup_enable=memory cgroup_memory=1
- install microk8s
    sudo snap install microk8s --classic --channel=lastest/stable
- configure microk8s
    - sudo usermod -a -G microk8s $USER
    - sudo chown -f -R $USER ~/.kube
    - su - $USER
    - microk8s status --wait-ready
- install addons for microk8s
    Not shure fi realy need... the masternode should provide this al
  - microk8s enable dns storage metallb prometheus helm3 ha-cluster
- Join the cluster
  - On raps4-01 
    - microk8s add-node
    - grep command
  - On new Node
    - exceute command
  - on any Node
    - check with k get node
  - maybe: drain









