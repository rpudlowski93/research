# ON-PREM KUBERNETES INSTALLATION TOOLS:

## RKE [link](https://github.com/rancher/rke) vs EPIPHANY [link](https://github.com/epiphany-platform/epiphany)

| Feature                                  | RKE                | RKE - description  | Epiphany           | Epiphany - description    |
| ---------------------------------------- | ------------------ | -------------------| ------------------ | ------------------------- |
| Opensource project                       | :white_check_mark: | https://github.com/rancher/rke | :white_check_mark: | https://github.com/epiphany-platform/epiphany |
| Upscale worker and control plane nodes   | :white_check_mark: | -                  | :white_check_mark: | -                         |
| Downscale worker and control plane nodes | :white_check_mark: | https://rancher.com/docs/rke/latest/en/managing-clusters/ | :x: | - |
| Kubeadm used                             | :x:                | -                  | :white_check_mark: | - |
| Simplified installation                  | :white_check_mark: | Installation is via a single binary and it uses a single YAML file, requires only docker-ce to be pre-installed | :white_check_mark: | |
| Support Single Node mode                 | :white_check_mark: | -                  | :white_check_mark: | - |
| Support HA-mode                          | :white_check_mark: | https://rancher.com/docs/rancher/v2.x/en/installation/resources/k8s-tutorials/ha-rke/ | :white_check_mark: | https://github.com/epiphany-platform/epiphany/blob/develop/docs/design-docs/kubernetes-ha/kubernetes-ha.md |
| Possible container runtimes              | Docker             | -                  | Docker             | - |
| Cluster state file                       | :white_check_mark: | State file is create by default what can be very useful in case of module approach | :x: | - |
| Simplicity                               | :white_check_mark: | Own solution for setting up a cluster based on the GO language | :x: | Complex solution for setting up a cluster based on python language, ansible tool (stateless) and kubeadm |
| Up-to-date K8s version                   | :white_check_mark: | The latest version of K8s with a slight delay | :x: | Usually two minor version behind the upstream version |
| Certificate Management                   | :white_check_mark: | RKE has a rke cert command and it is possible to easily rotate the auto-generated certificates | :x: ? | Epiphany generate custom certification for long time period |
| Offline mode                             | :x: | Not fully supported, we need to provide private Docker registry and the list of required docker images can be easily obtained | :white_check_mark: | - |
| Upgrade                                  | :white_check_mark: | ~50% faster upgrade than in Epiphany | :white_check_mark: | - |
| CNI network plugin supported             | :white_check_mark: | Flannel, Calico, Canal (by default), Weave | :white_check_mark: | Flannel, Calico, Canal |
| Customizability                          | :x: Limited by RKE project | - | :white_check_mark: Totally customizable |
| Cost                                     | :white_check_mark: Lower | - | :x: Higher | Epiphany team need to mantain all the code and upgrades
| CNCF Certification                       | :white_check_mark: | Every release supports the same APIs as upstream Kubernetes | :white_check_mark: | Every release supports the same APIs as upstream Kubernetes |
| Installation is idempotent               | :white_check_mark: | - | :white_check_mark: | - |
| Maintenance                              | :white_check_mark: | - 73 contributors<br /> Last month:<br /> - 8 authors of commits<br /> - 32 active PR<br /> - 26 merged PR<br /> - 13 releases | :white_check_mark: | - 23 contributors<br /> Last month:<br /> - 6 authors of commits<br /> - 36 active PR<br /> - 29 merged PR<br /> - 1 release |
| Troubleshooting                          | :white_check_mark: | - 153 open issues<br /> Last month:<br /> - 24 active issues<br /> - 14 closed issues | :white_check_mark: | - 298 open issues<br /> Last month:<br /> - 43 active issues<br /> - 18 closed issues |


What we still need to compare: 
- Air-gapped/Offline mode
- Limitation of the cluster installation 
- How faster the upgrade is in case of RKE
- Certificate management
- Installations
- Society of the projects (Maintenance, Troubleshooting)
- Documentation