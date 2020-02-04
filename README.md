项目致力于提供快速部署高可用`k8s`集群的工具, 同时也努力成为`k8s`实践、使用的参考书；基于二进制方式部署和利用`ansible-playbook`实现自动化；既提供一键安装脚本, 也可以根据`安装指南`分步执行安装各个组件。

- **集群特性** `TLS`双向认证、`RBAC`授权、[多Master高可用](docs/setup/00-planning_and_overall_intro.md#ha-architecture)、支持`Network Policy`、备份恢复、[离线安装](docs/setup/offline_install.md)
- **集群版本** kubernetes v1.13, v1.14, v1.15, v1.16
- **操作系统** CentOS/RedHat 7
- **运行时** docker 18.06.x-ce, 18.09.x, [containerd](docs/guide/containerd.md) 1.2.6
- **网络** [calico](docs/setup/network-plugin/calico.md), [cilium](docs/setup/network-plugin/cilium.md), [flannel](docs/setup/network-plugin/flannel.md), [kube-ovn](docs/setup/network-plugin/kube-ovn.md), [kube-router](docs/setup/network-plugin/kube-router.md)

## 安装指南

<table border="0">
    <tr>
        <td><a href="docs/00.planning.md">00-规划集群和配置介绍</a></td>
        <td><a href="docs/01.preinstall.md">01.安装前的准备</a></td>
        <td><a href="docs/setup/04-install_kube_master.md">04-安装master节点</a></td>
        <td><a href="docs/setup/06-install_network_plugin.md">06-安装集群网络</a></td>
    </tr>
    <tr>
        <td><a href="docs/setup/01-CA_and_prerequisite.md">01-创建证书和安装准备</a></td>
        <td><a href="docs/setup/01.preinstall.md">03-安装docker服务</a></td>
        <td><a href="docs/setup/05-install_kube_node.md">05-安装node节点</a></td>
        <td><a href="docs/setup/07-install_cluster_addon.md">07-安装集群插件</a></td>
    </tr>
</table>
