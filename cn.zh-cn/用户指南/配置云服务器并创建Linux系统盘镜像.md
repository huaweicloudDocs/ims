# 配置云服务器并创建Linux系统盘镜像<a name="ims_01_0231"></a>

## 操作场景<a name="section1693120251151"></a>

安装完操作系统后的临时云服务器需要进行相关配置，并安装原生的XEN和KVM驱动，才能保证后续创建的云服务器正常使用。

该任务指导用户完成Linux云服务器的相关配置与驱动安装，从而创建为Linux系统盘镜像。

## 操作步骤<a name="section1350115288165"></a>

1.  配置云服务器。

    具体操作请参考“[Linux外部镜像文件在导出前未完成初始化配置，怎么办？](https://support.huaweicloud.com/ims_faq/ims_faq_0012.html#section51410413191)”中的“步骤4：配置云服务器”。

    1.  配置网络
        -   检查云服务器的私有IP是否和控制台显示的私有IP一致（可以通过**ifconfig**查看）。如果不一致，请参考“[清理网络规则文件](https://support.huaweicloud.com/usermanual-ims/ims_01_0406.html)”清理网络规则文件。
        -   检查网卡属性是否为DHCP。如果云服务器网络配置为静态IP地址，请参考“[设置网卡属性为DHCP](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030713176.html)”修改为DHCP方式。
        -   检查SSH服务是否为开启状态（可以通过**service sshd status**查看）。如果未开启，请执行**service sshd start**。请确保您的云服务器防火墙（例如：Linux iptables）允许访问SSH。

    2.  安装驱动

        为了保证镜像创建的新云服务器的网络性能以及基本功能正常，必须在创建镜像时使用的云服务器中安装原生XEN和KVM驱动。在安装原生XEN和KVM驱动前，需要先卸载PV driver。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >建议您禁用任何防病毒软件或入侵检测软件，安装原生的XEN和KVM驱动完成后，您可以再次启用这些软件。

        -   卸载PV driver，请参考“[在Linux系统中卸载PV driver](https://support.huaweicloud.com/usermanual-ims/ims_01_0323.html)”。
        -   安装原生的XEN和KVM驱动，请参考“[安装原生的XEN和KVM驱动](https://support.huaweicloud.com/usermanual-ims/ims_01_0326.html)”。

        驱动安装完成后需要清除日志文件、历史记录等，请参考“[清除系统日志](https://support.huaweicloud.com/usermanual-ims/ims_01_0327.html)”。

    3.  配置文件系统
        -   修改grub文件的磁盘标识方式为UUID，请参考“[修改grub文件磁盘标识方式为UUID](https://support.huaweicloud.com/usermanual-ims/ims_01_0324.html)”。
        -   修改fstab文件的磁盘标识方式为UUID，请参考“[修改fstab文件磁盘标识方式为UUID](https://support.huaweicloud.com/usermanual-ims/ims_01_0325.html)”。
        -   清除“/etc/fstab”中非系统盘的自动挂载信息，避免对后续挂载数据盘可能带来影响。请参考“[卸载云服务器的数据盘](https://support.huaweicloud.com/usermanual-ims/ims_01_0410.html)”。

    4.  （可选）配置增值功能
        -   安装并配置Cloud-Init，请参考“[安装Cloud-Init工具](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030730603.html)”和“[配置Cloud-Init工具](https://support.huaweicloud.com/usermanual-ims/ims_01_0407.html)”。
        -   开启网卡多队列，请参考“[如何设置镜像的网卡多队列属性？](https://support.huaweicloud.com/ims_faq/ims_faq_0030.html)”。
        -   配置IPv6地址，请参考“[如何开启云服务器动态获取IPv6（试用）？](https://support.huaweicloud.com/ims_faq/ims_faq_0046.html)”。

2.  创建Linux系统盘镜像。

    具体操作请参考[通过云服务器创建Linux系统盘镜像](通过云服务器创建Linux系统盘镜像.md)。


## 后续操作<a name="section5471652205215"></a>

系统盘镜像创建成功后，请及时删除临时云服务器，避免继续产生费用。

