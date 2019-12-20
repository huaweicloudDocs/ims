# 安装原生的XEN和KVM驱动<a name="ims_01_0326"></a>

## 操作场景<a name="section15570104113511"></a>

在优化Linux私有镜像过程中，需要在云服务器上并安装原生的XEN和KVM驱动。

>![](public_sys-resources/icon-notice.gif) **须知：**   
>如果不安装XEN驱动，弹性云服务器的网络性能很差，并且安全组和防火墙也不会生效；  
>如果不安装KVM驱动，弹性云服务器的网卡可能无法检测到，无法与外部通信。因此，请您务必安装XEN和KVM驱动。  

请根据操作系统版本，修改不同的配置文件：

-   CentOS/EulerOS系列操作系统

    以CentOS 7.0为例，请修改“/etc/dracut.conf”文件，在add\_drivers项中添加xen-pv以及virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio）。驱动名之间以空格隔开，保存并退出“/etc/dracut.conf”文件，执行**dracut** **-f**命令，重新生成initrd。

    操作方法可参见[CentOS/EulerOS系列操作系统相关操作](#section57411552112542)。

-   Ubuntu/Debian系列系统

    请修改“/etc/initramfs-tools/modules”文件，添加xen-pv以及virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio）。驱动名之间以空格隔开，保存并退出“/etc/initramfs-tools/modules”文件，执行**update-initramfs** **-u**命令，重新生成initrd。

    操作方法可参见[Ubuntu/Debian系列操作系统相关操作](#section1865536911274)。

-   SUSE和OpenSUSE系列系统，根据操作系统版本不同，修改不同的配置文件。

    -   当操作系统版本低于SUSE 12 SP1或低于OpenSUSE 13时，请修改“/etc/sysconfig/kernel”文件，在INITRD\_MODULES=""添加xen-pv以及virtio的驱动（xen-pv驱动：xen\_vnif、xen\_vbd、xen\_platform\_pci；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio）。驱动名之间以空格隔开，执行**mkinitrd**命令，重新生成initrd。
    -   当操作系统版本为SUSE 12 SP1时，修改“/etc/dracut.conf”文件，在add\_drivers项中添加xen-pv以及virtio的驱动（xen-pv驱动：xen\_vnif、xen\_vbd、xen\_platform\_pci；virtio驱动：virtio\_blk、virtio\_scsi、virtio\_net、virtio\_pci、virtio\_ring、virtio）。驱动名之间以空格隔开，执行行**dracut** **-f**命令，重新生成initrd。
    -   当操作系统版本高于SUSE 12 SP1或高于OpenSUSE 13版本时，修改“/etc/dracut.conf”文件，在add\_drivers项中添加xen-pv和virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio）。驱动名之间以空格隔开，保存并退出“/etc/dracut.conf”文件，执行**dracut** **-f**命令，重新生成initrd。

    操作方法可参[SUSE/OpenSUSE系列操作系统相关操作](#section63790002112835)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >SUSE系列操作系统首先应确认OS是否已经安装了xen-kmp包（xen-pv的驱动包），执行以下命令：  
    >**rpm** **-qa** **|grep** **xen-kmp**  
    >回显类似如下：  
    >```  
    >xen-kmp-default-4.2.2_04_3.0.76_0.11-0.7.5  
    >```  
    >如果没有安装xen-kmp的包，请到ISO装机文件中获取并安装。  
    >如果误将built-in形式的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用。  


## 前提条件<a name="section19907254112223"></a>

-   对于使用Linux系统原生的XEN和KVM驱动的Linux云服务器，其内核版本必须高于2.6.24。
-   建议您禁用任何防病毒软件或入侵检测软件，安装原生的XEN和KVM驱动完成后，您可以再次启用这些软件。

## CentOS/EulerOS系列操作系统相关操作<a name="section57411552112542"></a>

1.  执行以下命令，打开“/etc/dracut.conf”文件。

    **vi** **/etc/dracut.conf**

2.  按“i”进入编辑模式，在“add\_drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

    ```
    [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
    # additional kernel modules to the default 
    add_drivers+="xen-blkfront xen-netfront virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio" 
    ……
    ```

3.  按“Esc”后，输入**:wq**，按“Enter”。 保存设置并退出“/etc/dracut.conf”文件。
4.  执行以下命令，重新生成initrd。

    **dracut** **-f** **/boot/initramfs-2.6.32-573.8.1.el6.x86\_64.img**

    如果引导的虚拟文件系统不是默认的initramfs，则命令为**：dracut** **-f** _实际使用的initramfs文件名或者initrd文件名_。“实际使用的initramfs文件名或者initrd文件名”可在grub.cfg配置（“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg”或“/boot/grub/grub. conf”，具体路径根据OS不同会有所区别）中获取。

5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **xen**

    **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **virtio**

    如果引导的虚拟文件系统是initrd，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **xen**

    **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **virtio**

    以引导的虚拟文件系统是initramfs为例，回显信息如下所示：

    ```
    [root@CTU10000xxxxx home]# lsinitrd /boot/initramfs-`uname -r`.img | grep xen 
    -rwxr--r--   1 root     root        54888 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/block/xen-blkfront.ko 
    -rwxr--r--   1 root     root        45664 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/net/xen-netfront.ko 
     
    [root@CTU10000xxxxx home]# lsinitrd /boot/initramfs-`uname -r`.img | grep virtio 
    -rwxr--r--   1 root     root        23448 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/block/virtio_blk.ko 
    -rwxr--r--   1 root     root        50704 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/net/virtio_net.ko 
    -rwxr--r--   1 root     root        28424 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/scsi/virtio_scsi.ko 
    drwxr-xr-x   2 root     root            0 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/virtio 
    -rwxr--r--   1 root     root        14544 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/virtio/virtio.ko 
    -rwxr--r--   1 root     root        21040 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/virtio/virtio_pci.ko 
    -rwxr--r--   1 root     root        18016 Jul 16 17:53 lib/modules/2.6.32-573.8.1.el6.x86_64/kernel/drivers/virtio/virtio_ring.ko
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改的方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
    >**cat** **/boot/config-\`uname -r\`** **|** **grep** **CONFIG\_VIRTIO** **|** **grep** **y**  
    >**cat** **/boot/config-\`uname -r\`** **|** **grep** **CONFIG\_XEN** **|** **grep** **y**  


## Ubuntu/Debian系列操作系统相关操作<a name="section1865536911274"></a>

1.  执行以下命令，打开“modules”文件。

    **vi** **/etc/initramfs-tools/modules**

2.  按“i”进入编辑模式，修改“/etc/initramfs-tools/modules”文件，添加xen-pv以及virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

    ```
    [root@CTU10000xxxxx ~]#vi /etc/initramfs-tools/modules 
    …… 
    # Examples: 
    # 
    # raid1 
    # sd_mOd 
    xen-blkfront
    xen-netfront
    virtio_blk
    virtio_scsi
    virtio_net
    virtio_pci
    virtio_ring
    virtio
    ```

3.  按“Esc”后，输入**:wq**，按“Enter”。保存设置并退出“/etc/initramfs-tools/modules”文件。
4.  执行以下命令，重新生成initrd。

    **update-initramfs** **-u**

5.  执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitramfs** **/boot/initrd.img-\`uname** **-r\`** **|grep** **xen**

    **lsinitramfs** **/boot/initrd.img-\`uname** **-r\`** **|grep** **virtio**

    ```
    [root@ CTU10000xxxxx home]# lsinitramfs /boot/initrd.img-`uname -r` |grep xen 
    lib/modules/3.5.0-23-generic/kernel/drivers/net/ethernet/qlogic/netxen 
    lib/modules/3.5.0-23-generic/kernel/drivers/net/ethernet/qlogic/netxen/netxen_nic.ko 
    lib/modules/3.5.0-23-generic/kernel/drivers/net/xen-netback 
    lib/modules/3.5.0-23-generic/kernel/drivers/net/xen-netback/xen-netback.ko 
    lib/modules/3.5.0-23-generic/kernel/drivers/block/xen-blkback 
    lib/modules/3.5.0-23-generic/kernel/drivers/block/xen-blkback/xen-blkback.ko 
     
    [root@ CTU10000xxxxx home]# lsinitramfs /boot/initrd.img-`uname -r` |grep virtio 
    lib/modules/3.5.0-23-generic/kernel/drivers/scsi/virtio_scsi.ko
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
    >```  
    >[root@ CTU10000xxxxx home]# cat /boot/config-`uname -r` | grep CONFIG_VIRTIO | grep y  
    >CONFIG_VIRTIO_BLK=y  
    >CONFIG_VIRTIO_NET=y  
    >CONFIG_VIRTIO=y  
    >CONFIG_VIRTIO_RING=y  
    >CONFIG_VIRTIO_PCI=y  
    >CONFIG_VIRTIO_MMIO_CMDLINE_DEVICES=y  
    >[root@ CTU10000xxxxx home]# cat /boot/config-`uname -r` | grep CONFIG_XEN | grep y  
    >CONFIG_XEN_BLKDEV_FRONTEND=y  
    >CONFIG_XEN_NETDEV_FRONTEND=y  
    >```  


## SUSE/OpenSUSE系列操作系统相关操作<a name="section63790002112835"></a>

当操作系统版本低于SUSE 12 SP1或低于OpenSUSE 13时，请修改“/etc/sysconfig/kernel”文件，操作步骤请参考[第一种情况](#zh-cn_topic_0037352187_li4339952312044)。

当操作系统版本为SUSE 12 SP1时，修改“/etc/dracut.conf”文件，添加xen-pv以及virtio的驱动，操作步骤请参考[第二种情况](#li45512494152649)。

当操作系统版本高于SUSE 12 SP1或高于OpenSUSE 13版本时，修改“/etc/dracut.conf”文件，在add\_drivers项中添加xen-pv和virtio的驱动，操作步骤请参考[第三种情况](#zh-cn_topic_0037352187_li57696863113515)。

-   <a name="zh-cn_topic_0037352187_li4339952312044"></a>当操作系统版本低于SUSE 12 SP1或低于OpenSUSE 13时，操作步骤如下。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >SUSE系列操作系统首先应确认OS是否已经安装了xen-kmp包（xen-pv的驱动包），执行如下命令：  
    >**rpm** **-qa** **|grep** **xen-kmp**  
    >回显类似如下：  
    >```  
    >xen-kmp-default-4.2.2_04_3.0.76_0.11-0.7.5  
    >```  
    >如果没有安装xen-kmp的包，请到安装ISO中获取并安装。  

    1.  执行如下命令，修改“/etc/sysconfig/kernel”文件。

        ****vi**** **etc/sysconfig/kernel**

    2.  在INITRD\_MODULES=""中添加xen-pv以及virtio的驱动（具体格式要根据OS本身的要求来决定）。

        ```
        SIA10000xxxxx:~ # vi /etc/sysconfig/kernel 
        # (like drivers for scsi-controllers, for lvm or reiserfs)
        #
        INITRD_MODULES="ata_piix ata_generic xen_vnif xen_vbd xen_platform_pci virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"
        ```

    3.  执行**mkinitrd**命令，重新生成initrd。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果引导的虚拟文件系统不是默认的initramfs或者initrd，则命令为：**dracut -f** _实际使用的initramfs或者initrd文件名_。“实际使用的initramfs或者initrd文件名”可在menu.lst或者grub.cfg配置（“/boot/grub/menu.lst”或“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg”）中获取。  

        以SUSE 11 SP4为例，如下所示：

        ```
        default 0
        timeout 10
        gfxmenu (hd0,0)/boot/message
        title sles11sp4_001_[_VMX_]
        root (hd0,0)
        kernel /boot/linux.vmx vga=0x314 splash=silent console=ttyS0,115200n8 console=tty0 net.ifnames=0 NON_PERSISTENT_DEVICE_NAMES=1 showopts
        initrd /boot/initrd.vmx
        title Failsafe_sles11sp4_001_[_VMX_]
        root (hd0,0)
        kernel /boot/linux.vmx vga=0x314 splash=silent ide=nodma apm=off noresume edd=off powersaved=off nohz=off highres=off processsor.max+cstate=1 nomodeset x11failsafe console=ttyS0,115200n8 console=tty0 net.ifnames=0 NON_PERSISTENT_DEVICE_NAMES=1 showopts
        initrd /boot/initrd.vmx
        ```

        其中，initrd所在行的/boot/initrd.vmx为实际使用的initrd文件，执行的时候请按照**dracut** **-f** **/boot/initrd.vmx**执行。如果initrd所在行的initrd文件不包含/boot目录，如/initramfs-xxx，请在执行dracut命令时增加boot目录，例如：**dracut** **-f** **/boot/initramfs-xxx**。

    4.  执行如下命令，检查是否已经成功装载了XEN的PVOPS或者KVM的virtio相应模块。

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **xen**

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **virtio**

        ```
        SIA10000xxxxx:~ # lsinitrd /boot/initrd-`uname -r` | grep xen
        -rwxr--r-- 1 root root 42400 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/block/xen-blkfront.ko
        -rwxr--r-- 1 root root 44200 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/net/xen-netfront.ko
        
        SIA10000xxxxx:~ # lsinitrd /boot/initrd-`uname -r` | grep virtio
        -rwxr--r-- 1 root root 19248 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/scsi/virtio_scsi.ko
        -rwxr--r-- 1 root root 23856 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/block/virtio_blk.ko
        drwxr-xr-x 2 root root 0 Jul 12 14:53 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio
        -rwxr--r-- 1 root root 15848 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio_ring.ko
        -rwxr--r-- 1 root root 20008 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio_pci.ko
        -rwxr--r-- 1 root root 12272 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio.ko
        -rwxr--r-- 1 root root 38208 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/net/virtio_net.ko
        ```

    5.  重启云服务器。
    6.  重启完毕后，修改“/boot/grub/menu.lst”文件，增加xen\_platform\_pci.dev\_unplug=all和修改root的配置。

        修改前如下所示：

        ```
        ###Don't change this comment -YaST2 identifier: Original name: linux###
        title SUSE Linux Enterprise Server 11SP4 - 3.0.76-0.11 (default) 
        root (hd0,0) 
        kernel /boot/vmlinuz-3.0.76-0.11-default root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130 splash=silentcrashkernel=256M-:128M showopts vga=0x314
        initrd /boot/initrd-3.0.76-0.11-default
        ```

        修改后如下所示：

        ```
        ###Don't change this comment -YaST2 identifier: Original name: linux###
        title SUSE Linux Enterprise Server 11SP4 - 3.0.76-0.11 (default) 
        root (hd0,0) 
        kernel /boot/vmlinuz-3.0.76-0.11-default root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130 splash=silentcrashkernel=256M-:128M showopts vga=0x314 xen_platform_pci.dev_unplug=all 
        initrd /boot/initrd-3.0.76-0.11-default
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >-   确保磁盘root分区为UUID的表示形式。  
        >-   xen\_platform\_pci.dev\_unplug=all该参数的添加是为了屏蔽qemu设备。  
        >-   SUSE 11 SP1 64bit \~ SUSE 11 SP4 64bit系统需要在“menu.lst”文件添加xen\_platform\_pci.dev\_unplug=all，SUSE 12以后版本默认启用此功能，无需配置。  

    7.  执行如下命令确认initrd中是否存在XEN驱动。

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **xen**

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **virtio**

        ```
        SIA10000xxxxx:~ # lsinitrd /boot/initrd-`uname -r` | grep xen
        -rwxr--r-- 1 root root 42400 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/block/xen-blkfront.ko
        -rwxr--r-- 1 root root 44200 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/net/xen-netfront.ko
        
        SIA10000xxxxx:~ # lsinitrd /boot/initrd-`uname -r` | grep virtio
        -rwxr--r-- 1 root root 19248 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/scsi/virtio_scsi.ko
        -rwxr--r-- 1 root root 23856 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/block/virtio_blk.ko
        drwxr-xr-x 2 root root 0 Jul 12 14:53 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio
        -rwxr--r-- 1 root root 15848 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio_ring.ko
        -rwxr--r-- 1 root root 20008 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio_pci.ko
        -rwxr--r-- 1 root root 12272 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/virtio/virtio.ko
        -rwxr--r-- 1 root root 38208 Jun 22 2012 lib/modules/2.6.32-279.el6.x86_64/kernel/drivers/net/virtio_net.ko
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
        >**cat** **/boot/config-\`uname** **-r\`** **|** **grep** **CONFIG\_VIRTIO** **|** **grep** **y**  
        >**cat** **/boot/config-\`uname** **-r\`** **|** **grep** **CONFIG\_XEN** **|** **grep** **y**  


-   <a name="li45512494152649"></a>当操作系统版本为SUSE 12 SP1时，操作步骤如下。
    1.  执行以下命令，打开“/etc/dracut.conf”文件。

        **vi** **/etc/dracut.conf**

    2.  按“i”进入编辑模式，在“add-drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

        ```
        [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
        # additional kernel modules to the default
        add_drivers+="ata_piix ata_generic xen_vnif xen_vbd xen_platform_pci virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"
        ```

    3.  按“Esc”后，输入**:wq**，按“Enter”。 保存设置并退出“/etc/dracut.conf”文件。
    4.  执行以下命令，重新生成initrd。

        **dracut** **-f** **/boot/**initramfs**-******_文件名_

        如果引导的虚拟文件系统不是默认的initramfs，则命令为：**dracut** **-f** _实际使用的initramfs文件名或者initrd文件名_。“实际使用的initramfs文件名或者initrd文件名”可在grub.cfg配置（“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg”或“/boot/grub/grub.conf”，具体路径根据OS不同会有所不同）中获取。

    5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **xen**

        **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **virtio**

        如果引导的虚拟文件系统是initrd，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **xen**

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **virtio**


-   <a name="zh-cn_topic_0037352187_li57696863113515"></a>当操作系统版本高于SUSE 12 SP1或高于OpenSUSE 13版本时，操作步骤如下。

    以SUSE Linux Enterprise Server 12 SP2 \(x86\_64\)为例，如下所示：

    1.  执行以下命令，打开“/etc/dracut.conf”文件。

        **vi** **/etc/dracut.conf**

    2.  按“i”进入编辑模式，在“add\_drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

        ```
        [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
        # additional kernel modules to the default
        add_drivers+="ata_piix ata_generic xen-blkfront xen-netfront virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"
        ```

    3.  按“Esc”后，输入**:wq**，按“Enter”。 保存设置并退出“/etc/dracut.conf”文件。
    4.  执行以下命令，重新生成initrd。

        **dracut** **-f** **/boot/**initramfs**-******_文件名_

        如果引导的虚拟文件系统不是默认的initramfs，则命令为：**dracut** **-f** _实际使用的initramfs文件名或者initrd文件名_。“实际使用的initramfs文件名或者initrd文件名”可在grub.cfg配置（“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg”或“/boot/grub/grub. conf”，具体路径根据OS不同会有所区别）中获取。

    5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **xen**

        **lsinitrd** **/boot/initramfs-\`uname** **-r\`.img** **|** **grep** **virtio**

        如果引导的虚拟文件系统是initrd ，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **xen**

        **lsinitrd** **/boot/initrd-\`uname** **-r\`** **|** **grep** **virtio**

        以引导的虚拟文件系统是initrd为例，回显信息如下所示：

        ```
        sluo-ecs-30dc:~ # lsinitrd /boot/initrd-`uname -r` | grep xen
        -rw-r--r-- 1 root root 69575 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/block/xen-blkfront.ko
        -rw-r--r-- 1 root root 53415 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/net/xen-netfront.ko
        drwxr-xr-x 2 root root 0 Sep 28 10:21 lib/modules/4.4.21-69-default/updates/pvdriver/xen-hcall
        -rwxr-xr-x 1 root root 8320 Sep 28 10:21 lib/modules/4.4.21-69-default/updates/pvdriver/xen-hcall/xen-hcall.ko
        
        sluo-ecs-30dc:~ # lsinitrd /boot/initrd-`uname -r` | grep virtio
        -rw-r--r-- 1 root root 29335 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/block/virtio_blk.ko
        -rw-r--r-- 1 root root 57007 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/net/virtio_net.ko
        -rw-r--r-- 1 root root 32415 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/scsi/virtio_scsi.ko
        drwxr-xr-x 2 root root 0 Sep 28 10:21 lib/modules/4.4.21-69-default/kernel/drivers/virtio
        -rw-r--r-- 1 root root 19623 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/virtio/virtio.ko
        -rw-r--r-- 1 root root 38943 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/virtio/virtio_pci.ko
        -rw-r--r-- 1 root root 24431 Oct 26 2016 lib/modules/4.4.21-69-default/kernel/drivers/virtio/virtio_ring.ko
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
        >**cat** **/boot/config-\`uname** **-r\`** **|** **grep** **CONFIG\_VIRTIO** **|** **grep** **y**  
        >**cat** **/boot/config-\`uname** **-r\`** **|** **grep** **CONFIG\_XEN** **|** **grep** **y**  



