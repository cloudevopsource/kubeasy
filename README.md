项目提供快速部署高可用`k8s`集群的工具, 同时也努力成为`k8s`实践、使用的参考书；基于二进制方式部署和利用`ansible-playbook`实现自动化；既提供一键安装脚本, 也可以根据`安装指南`分步执行安装各个组件。

- **集群特性** `TLS`双向认证、`RBAC`授权、[多Master高可用](docs/setup/00-planning_and_overall_intro.md#ha-architecture)、支持`Network Policy`、备份恢复、[离线安装](docs/setup/offline_install.md)
- **集群版本** kubernetes v1.13, v1.14, v1.15, v1.16
- **操作系统** CentOS/RedHat 7
- **运行时** docker 18.06.x-ce, 18.09.x, [containerd](docs/guide/containerd.md) 1.2.6
- **网络** [calico](docs/setup/network-plugin/calico.md), [cilium](docs/setup/network-plugin/cilium.md), [flannel](docs/setup/network-plugin/flannel.md), [kube-ovn](docs/setup/network-plugin/kube-ovn.md), [kube-router](docs/setup/network-plugin/kube-router.md)

