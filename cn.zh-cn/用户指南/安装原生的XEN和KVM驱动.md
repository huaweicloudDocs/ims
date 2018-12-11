# 安装原生的XEN和KVM驱动<a name="ZH-CN_TOPIC_0086020894"></a>

## 操作场景<a name="section15570104113511"></a>

在优化Linux私有镜像过程中，需要在云服务器上并安装原生的XEN和KVM驱动。

请根据操作系统版本不同，修改不同的配置文件：

-   CentOS/Red Hat/Oracle系列操作系统。

    以CentOS 7.0为例，请修改“/etc/dracut.conf”文件，在add\_drivers项中添加xen-pv以及virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio），驱动名之间以空格隔开，保存并退出/etc/dracut.conf文件，执行**dracut -f**命令，重新生成initrd。

    操作方法可参见[CentOS/Red Hat/Oracle系列操作系统相关操作](#section57411552112542)。

-   Ubuntu/Debian系列系统。

    请修改/etc/initramfs-tools/modules文件，添加xen-pv以及virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio），驱动名之间是空格隔开，保存并退出/etc/initramfs-tools/modules文件，执行**update-initramfs -u**命令，重新生成initrd。

    操作方法可参见[Ubuntu/Debian系列操作系统相关操作](#section1865536911274)。

-   SUSE和openSUSE系列系统，根据操作系统版本不同，修改不同的配置文件。

    -   当操作系统版本低于SUSE12 SP1时，低于openSUSE13时，请修改/etc/sysconfig/kernel文件，在INITRD\_MODULES=""添加xen-pv以及virtio的驱动（xen-pv驱动：xen\_vnif、xen\_vbd、xen\_platform\_pci；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio），驱动名之间是空格隔开，执行**mkinitrd**命令，重新生成initrd。
    -   当操作系统版本为SUSE12 SP1时，修改/etc/dracut.conf文件，在“add-drivers”项中添加xen-pv以及virtio的驱动（xen-pv驱动：xen\_vnif、xen\_vbd、xen\_platform\_pci；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio），驱动名之间是空格隔开，执行行**dracut -f**命令，重新生成initrd。
    -   当操作系统版本高于SUSE12 SP1或高于openSUSE13版本时，修改/etc/dracut.conf文件，在“add-drivers”项中添加xen-pv和virtio的驱动（xen-pv驱动：xen-blkfront、xen-netfront；virtio驱动：virtio\_blk、virtio\_scsi 、virtio\_net、virtio\_pci、virtio\_ring、virtio），驱动名之间以空格隔开，保存并退出/etc/dracut.conf文件，执行**dracut -f**命令，重新生成initrd。

    操作方法可参[SUSE/openSUSE系列操作系统相关操作](#section63790002112835)。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >SUSE系列操作系统首先应确认OS已经安装了xen-kmp包\(xen-pv的驱动包\)：  
    >linux-s27m:\~  **\# rpm -qa |grep xen-kmp**  
    >回显类似如下：  
    >```  
    >xen-kmp-default-4.2.2_04_3.0.76_0.11-0.7.5  
    >```  
    >如果没有安装xen-kmp的包，请到安装ISO中获取并安装。  
    >如果误将built-in形式的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用。  


## 前提条件<a name="section19907254112223"></a>

对于使用Linux系统原生的XEN和KVM驱动，而不使用Tools的Linux云服务器，其Linux的内核版本必须高于2.6.24。

## CentOS/Red Hat/Oracle系列操作系统相关操作<a name="section57411552112542"></a>

1.  执行以下命令，打开“/etc/dracut.conf”文件。

    **vi /etc/dracut.conf**

2.  按“i”进入编辑模式，在“add-drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

    ```
    [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
    # additional kernel modules to the default 
    add_drivers+="xen-blkfront xen-netfront virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio" 
    ……     
    ```

3.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出/etc/dracut.conf文件。
4.  执行以下命令，重新生成initrd。

    **dracut -f /boot/initramfs-2.6.32-573.8.1.el6.x86\_64.img**

    如果引导的虚拟文件系统不是默认的initramfs，则命令为**：dracut -f 实际使用的initramfs**文件名**或者initrd文件名**。实际使用的initramfs文件名或者initrd文件名可在grub.cfg配置（/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg或“/boot/grub/grub. conf”，具体路径根据OS不同会有所不同）中获取。

5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitrd /boot/initramfs-\`uname -r\`.img | grep xen**

    **lsinitrd /boot/initramfs-\`uname -r\`.img | grep virtio**

    如果引导的虚拟文件系统是initrd ，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitrd /boot/initrd-\`uname -r\` | grep xen**

    **lsinitrd /boot/initrd-\`uname -r\` | grep virtio**

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
    >\[root@ CTU10000xxxxx home\]**\# cat /boot/config-\`uname -r\` | grep CONFIG\_VIRTIO | grep y**  
    >\[root@ CTU10000xxxxx home\]**\# cat /boot/config-\`uname -r\` | grep CONFIG\_XEN | grep y**  

6.  Oracle操作系统请修改GuestOS镜像配置，添加nosmap内核启动参数，禁止内核启用smap特性。

    Oracle6.x系列操作系统请修改/boot/grub/grub.conf， Oracle7.x系列操作系统修改/boot/grub2/grub.cfg，添加nosmap。

    以Oracle Linux Server 7.1操作系统为例，请执行如下操作。

    1.  执行如下命令，编辑grub配置文件。

        **vi /boot/grub2/grub.cfg**

    2.  找到“Oracle Linux Server 7.1, with Unbreakable Enterprise Kernel”启动项配置文件，并添加nosmap。

        ```
        menuentry '*Oracle Linux Server 7.1, with Unbreakable Enterprise Kernel *3.8.13-55.1.6.el7uek.x86_64' –class ol --class gnu-linux --class gnu --class os --unrestricted $menuentry_id_option 'gnulinux-3.8.13-55.1.6.el7uek.x86_64-advanced-87e8ef66-eb1e-4afc-892e-c3e38cb29c94' {
                load_video
                set gfxpayload=keep
                insmod gzio
                insmod part_msdos
                insmod ext2
                set root='hd0,msdos1'
                if [ x$feature_platform_search_hint = xy ]; then
                  search --no-floppy --fs-uuid --set=root --hint-bios=hd0,msdos1 --hint-efi=hd0,msdos1 --hint-baremetal=ahci0,msdos1 --hint='hd0,msdos1'  07110be5-4942-447e-8d0c-001e97342c85
                else
                  search --no-floppy --fs-uuid --set=root 07110be5-4942-447e-8d0c-001e97342c85
                fi
                linux16 /vmlinuz-3.8.13-55.1.6.el7uek.x86_64 root=UUID=87e8ef66-eb1e-4afc-892e-c3e38cb29c94 crashkernel=auto console=tty0 console=ttyS0 net.ifnames=0 nosmap
                initrd16 /initramfs-3.8.13-55.1.6.el7uek.x86_64.img
        }
        ```



## Ubuntu/Debian系列操作系统相关操作<a name="section1865536911274"></a>

1.  执行以下命令，打开**modules**文件。

    **vi /etc/initramfs-tools/modules**

2.  按“i”进入编辑模式，修改/etc/initramfs-tools/modules文件，添加xen-pv以及virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

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

3.  按“Esc”后，输入“:wq”，按“Enter”。保存设置并退出“/etc/initramfs-tools/modules”文件。
4.  执行以下命令，重新生成initrd。

    **update-initramfs -u**

5.  执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

    **lsinitramfs /boot/initrd.img-\`uname -r\` |grep xen**

    **lsinitramfs /boot/initrd.img-\`uname -r\` |grep virtio**

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
    >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改的方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
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


## SUSE/openSUSE系列操作系统相关操作<a name="section63790002112835"></a>

当操作系统版本低于SUSE12 SP1时，低于openSUSE13时，请修改/etc/sysconfig/kernel文件，在INITRD\_MODULES=""添加xen-pv以及virtio的驱动，操作步骤请参考[当操作系统版本低于SUSE12 SP1时，低于o...](#zh-cn_topic_0037352187_li4339952312044)。

当操作系统版本为SUSE12 SP1时，修改/etc/dracut.conf文件，添加xen-pv以及virtio的驱动，操作步骤请参考[当操作系统版本为SUSE12 SP1...](#li45512494152649)。

当操作系统版本高于SUSE12 SP1或高于openSUSE13版本时，修改/etc/dracut.conf文件，在“add-drivers”项中添加xen-pv和virtio的驱动，操作步骤请参考[SUSE12以上和openSUSE13以上...](#zh-cn_topic_0037352187_li57696863113515)。

-   <a name="zh-cn_topic_0037352187_li4339952312044"></a>当操作系统版本低于SUSE12 SP1时，低于openSUSE13时，操作步骤如下。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >SUSE系列操作系统首先应确认OS已经安装了xen-kmp包\(xen-pv的驱动包\)：  
    >**linux-s27m:\~ \# rpm -qa |grep xen-kmp**  
    >回显类似如下：  
    >```  
    >xen-kmp-default-4.2.2_04_3.0.76_0.11-0.7.5  
    >```  
    >如果没有安装xen-kmp的包，请到安装ISO中获取并安装。  

    1.  执行如下命令，修改/etc/sysconfig/kernel文件。

        ****vi **etc/sysconfig/kernel**

    2.  在INITRD\_MODULES=""添加xen-pv以及virtio的驱动（具体格式要根据OS本身的要求来决定）。

        ```
        SIA10000xxxxx:~ # vi /etc/sysconfig/kernel 
        # (like drivers for scsi-controllers, for lvm or reiserfs)
        #
        INITRD_MODULES="ata_piix ata_generic xen_vnif xen_vbd xen_platform_pci virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"
        ```

    3.  执行**mkinitrd**命令，重新生成initrd。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >如果引导的虚拟文件系统不是默认的initramfs或者initrd，则命令为：**dracut -f 实际使用的initramfs或者initrd文件名**。实际使用的initramfs或者initrd文件名可在menu.lst或者grub.cfg配置（“/boot/grub/menu.lst”或“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg”）中获取。  

        以SUSE 11SP4为例如下所示：

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

        其中，initrd所在行的/boot/initrd.vmx为实际使用的initrd文件，执行的时候请按照dracut -f /boot/initrd.vmx执行。如果initrd所在行的initrd文件不包含/boot目录，如/initramfs-xxx，请在执行dracut命令时增加boot目录，例如：dracut -f /boot/initramfs-xxx。

    4.  执行如下命令，检查是否已经成功装载了XEN的PVOPS或者KVM的virtio相应模块。

        **lsinitrd /boot/initrd-\`uname -r\` | grep xen**

        **lsinitrd /boot/initrd-\`uname -r\` | grep virtio**

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
    6.  重启完毕后，参考如下步骤进行云服务器内参数的修改。
        1.  修改“/boot/grub/menu.lst”文件，增加xen\_platform\_pci.dev\_unplug=all和修改root和resume的配置。

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
            >-   SUSE11 SP1 64bit \~SUSE11 SP4 64bit系统需要在menu.lst文件添加xen\_platform\_pci.dev\_unplug=all，SUSE12以后版本默认启用此功能，无需配置。  


    7.  执行如下命令确认initrd中是否存在XEN驱动。

        **lsinitrd /boot/initrd-\`uname -r\` | grep xen**

        **lsinitrd /boot/initrd-\`uname -r\` | grep virtio**

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
        >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改的方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
        >SIA10000xxxxx:\~  **\# cat /boot/config-\`uname -r\` | grep CONFIG\_VIRTIO | grep y**  
        >SIA10000xxxxx:\~  **\# cat /boot/config-\`uname -r\` | grep CONFIG\_XEN | grep y**  


-   <a name="li45512494152649"></a>当操作系统版本为SUSE12 SP1时，操作步骤如下。
    1.  执行以下命令，打开“/etc/dracut.conf”文件。

        **vi /etc/dracut.conf**

    2.  按“i”进入编辑模式，在“add-drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

        ```
        [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
        # additional kernel modules to the default
        add_drivers+="ata_piix ata_generic xen_vnif xen_vbd xen_platform_pci virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"
        ```

    3.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出/etc/dracut.conf文件。
    4.  执行以下命令，重新生成initrd。

        **dracut -f /boot/**initramfs**-_文件名_******

        如果引导的虚拟文件系统不是默认的initramfs，则命令为**：dracut -f 实际使用的initramfs**文件名**或者initrd文件名**。实际使用的initramfs文件名或者initrd文件名可在grub.cfg配置（/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg或“/boot/grub/grub. conf”，具体路径根据OS不同会有所不同）中获取。

    5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd /boot/initramfs-\`uname -r\`.img | grep xen**

        **lsinitrd /boot/initramfs-\`uname -r\`.img | grep virtio**

        如果引导的虚拟文件系统是initrd ，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd /boot/initrd-\`uname -r\` | grep xen**

        **lsinitrd /boot/initrd-\`uname -r\` | grep virtio**


-   <a name="zh-cn_topic_0037352187_li57696863113515"></a>当操作系统版本高于SUSE12 SP1或高于openSUSE13版本时，操作步骤如下。

    以SUSE Linux Enterprise Server 12 SP2 \(x86\_64\)为例如下所示：

    1.  执行以下命令，打开“/etc/dracut.conf”文件。

        **vi /etc/dracut.conf**

    2.  按“i”进入编辑模式，在“add-drivers”项中添加xen-pv和virtio的驱动（具体格式要根据操作系统本身的要求来决定）。

        ```
        [root@CTU10000xxxxx ~]# vi /etc/dracut.conf 
        # additional kernel modules to the default
        add_drivers+="ata_piix ata_generic xen-blkfront xen-netfront virtio_blk virtio_scsi virtio_net virtio_pci virtio_ring virtio"  
        ```

    3.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出/etc/dracut.conf文件。
    4.  执行以下命令，重新生成initrd。

        **dracut -f /boot/**initramfs**-_文件名_******

        如果引导的虚拟文件系统不是默认的initramfs，则命令为**：dracut -f 实际使用的initramfs**文件名**或者initrd文件名**。实际使用的initramfs文件名或者initrd文件名可在grub.cfg配置（/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg或“/boot/grub/grub. conf”，具体路径根据OS不同会有所不同）中获取。

    5.  如果引导的虚拟文件系统是initramfs，执行以下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd /boot/initramfs-\`uname -r\`.img | grep xen**

        **lsinitrd /boot/initramfs-\`uname -r\`.img | grep virtio**

        如果引导的虚拟文件系统是initrd ，执行如下命令，检查是否已经成功装载了原生的XEN和KVM驱动相应模块。

        **lsinitrd /boot/initrd-\`uname -r\` | grep xen**

        **lsinitrd /boot/initrd-\`uname -r\` | grep virtio**

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
        >如果误将built-in形式存在内核中的驱动添加到initrd或initramfs文件中，不会影响云服务器正常使用，这里全写进去只是为了修改的方便，但是使用lsinitrd命令无法检查到。可使用如下方法确定这些驱动是否以built-in形式存在内核中，例如：  
        >SIA10000xxxxx:\~  **\# cat /boot/config-\`uname -r\` | grep CONFIG\_VIRTIO | grep y**  
        >SIA10000xxxxx:\~  **\# cat /boot/config-\`uname -r\` | grep CONFIG\_XEN | grep y**  



