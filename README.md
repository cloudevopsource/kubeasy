項目提供快速部署高可用`k8s`集群的工具, 同時也努力成為`k8s`實踐、使用的參考書；基於二進制方式部署和利用`ansible-playbook`實現自動化；既提供壹鍵安裝腳本, 也可以根據`安裝指南`分步執行安裝各個組件。

- **集群特性** `TLS`雙向認證、`RBAC`授權、[多Master高可用](docs/setup/00-planning_and_overall_intro.md#ha-architecture)、支持`Network Policy`、備份恢復、[離線安裝](docs/setup/offline_install.md)
- **集群版本** kubernetes v1.13, v1.14, v1.15, v1.16
- **操作系統** CentOS/RedHat 7
- **運行時** docker 18.06.x-ce, 18.09.x, [containerd](docs/guide/containerd.md) 1.2.6
- **網絡** [calico](docs/setup/network-plugin/calico.md), [cilium](docs/setup/network-plugin/cilium.md)