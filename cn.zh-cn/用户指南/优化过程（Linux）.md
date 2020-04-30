# 优化过程（Linux）<a name="zh-cn_topic_0047501133"></a>

为了同时支持XEN虚拟化和KVM虚拟化，Linux弹性云服务器的正常运行需依赖于xen-pv驱动、virtio驱动等，因此，XEN实例变更为KVM实例前，需要确保Linux私有镜像已完成相关配置，包括安装驱动、修改UUID等。同时，优化私有镜像也能提升弹性云服务器的网络性能。

1.  将待优化的Linux镜像创建弹性云服务器，并开机登录。
2.  卸载弹性云服务器操作系统中安装的PV Driver。

    具体操作请参见[在Linux系统中卸载PV driver](在Linux系统中卸载PV-driver.md)。

3.  修改grub文件磁盘标识方式为UUID。

    具体操作请参见[修改grub文件磁盘标识方式为UUID](修改grub文件磁盘标识方式为UUID.md)。

4.  修改fstab文件磁盘标识方式为UUID。

    具体操作请参见[修改fstab文件磁盘标识方式为UUID](修改fstab文件磁盘标识方式为UUID.md)。

5.  安装原生的XEN和KVM驱动。

    具体操作请参见[安装原生的XEN和KVM驱动](安装原生的XEN和KVM驱动.md)。

6.  清除日志文件、历史记录等，关闭云服务器。

    具体操作请参见[清除日志文件](清除日志文件.md)。

7.  通过弹性云服务器创建Linux私有镜像。

