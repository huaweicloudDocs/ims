# 优化过程\(Linux\)<a name="ZH-CN_TOPIC_0047501133"></a>

为了同时支持XEN虚拟化和KVM虚拟化，Linux弹性云服务器的正常运行需依赖于xen-pv驱动、virtio驱动等，因此，XEN实例变更为KVM实例前，需要确保Linux弹性云服务器已完成相关配置，包括安装驱动、修改UUID等。

1.  将待优化的Linux镜像创建弹性云服务器，并开机登录。
2.  卸载云服务器操作系统中安装的PV Driver。

    具体操作请参见[在Linux系统中卸载PV Driver](在Linux系统中卸载PV-Driver.md)。

3.  修改grub的UUID。

    具体操作请参见[修改grub文件磁盘标识方式为UUID](修改grub文件磁盘标识方式为UUID.md)。

4.  修改fstab的UUID。

    具体操作请参见[修改fstab文件磁盘标识方式为UUID](修改fstab文件磁盘标识方式为UUID.md)。

5.  安装原生的XEN和KVM驱动。

    具体操作请参见[安装原生的XEN和KVM驱动](安装原生的XEN和KVM驱动.md)。

6.  清除日志文件、历史记录等，关闭云服务器。
7.  通过弹性云服务器创建Linux私有镜像。

