# 设置网卡属性为DHCP（Linux）<a name="zh-cn_topic_0030713176"></a>

## 操作场景<a name="zh-cn_topic_0029124465_section2104193419393"></a>

通过云服务器或者外部镜像文件创建私有镜像时，如果云服务器或镜像文件所在虚拟机的网络配置是静态IP地址时，您需要修改网卡属性为DHCP，以使私有镜像发放的新云服务器可以动态获取IP地址。

不同操作系统配置方法略有区别，请参考对应操作系统的相关资料进行操作。

>![](public_sys-resources/icon-note.gif) **说明：** 
>使用外部镜像文件创建私有镜像时，设置网卡属性操作需要在虚拟机内部完成，建议您在原平台的虚拟机实施修改后，再导出镜像。

## 前提条件<a name="zh-cn_topic_0029124465_section50735044162237"></a>

已登录创建Linux私有镜像所使用的云服务器。

登录云服务器的详细操作请参见“[Linux弹性云服务器登录方式概述](https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0013771089.html)”。

## 操作步骤<a name="zh-cn_topic_0029124465_section5756595193936"></a>

本节操作以Ubuntu 16.04操作系统为例，介绍检查及设置云服务器网卡属性的方法。

1.  在云服务器上执行以下命令，使用vi编辑器打开“/etc/network/interfaces”文件，查看网卡的网络配置。

    **vi /etc/network/interfaces**

    -   信息显示所有网卡的网络配置为DHCP模式时，无需重复设置网卡属性，输入**:q**退出编辑器。

        ```
        auto lo
        iface lo inet loopback
        auto eth0
        iface eth0 inet dhcp
        
        auto eth1
        iface eth1 inet dhcp
        ```

    -   信息显示网卡的网络配置为静态IP地址时，请执行[2](#zh-cn_topic_0029124465_li47654828194142)。

        ```
        auto lo
        iface lo inet loopback
        auto eth0
        #iface eth0 inet dhcp
        iface eth0 inet static
        address 192.168.1.109
        netmask 255.255.255.0
        gateway 192.168.1.1
        ```

2.  <a name="zh-cn_topic_0029124465_li47654828194142"></a>按“i”进入编辑模式。
3.  删除静态IP设置的相关内容，然后将对应的网卡设置为DHCP方式。

    您也可以使用“\#”注释掉静态IP设置的相关内容。

    ```
    auto lo
    iface lo inet loopback
    auto eth0
    iface eth0 inet dhcp
    ```

    如果您有多个网卡，请将剩余网卡按照上述方法设置为DHCP方式。

    ```
    auto lo
    iface lo inet loopback
    auto eth0
    iface eth0 inet dhcp
    auto eth1
    iface eth1 inet dhcp
    ```

4.  按“ESC”后，输入**:wq**，按“Enter”。

    保存设置并退出编辑器。


## 相关操作<a name="section5134195521117"></a>

您还可以配置DHCP持续获取IP地址能力，根据云服务器操作系统选择对应的操作。

-   CentOS系列/EulerOS系列：使用vi编辑器在“/etc/sysconfig/network-scripts/ifcfg-ethX”配置文件中添加PERSISTENT\_DHCLIENT="y"。
-   SUSE系列：使用vi编辑器将“/etc/sysconfig/network/dhcp”配置文件中的DHCLIENT\_USE\_LAST\_LEASE设置为no。
-   Ubuntu 12.04及以上版本：将dhclient升级为ISC dhclient 4.2.4以支持网卡持续DHCP获取IP地址能力。请自行安装isc-dhcp-server进行升级。

