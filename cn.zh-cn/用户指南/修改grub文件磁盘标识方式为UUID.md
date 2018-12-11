# 修改grub文件磁盘标识方式为UUID<a name="ZH-CN_TOPIC_0086020895"></a>

## 操作场景<a name="section1156634615414"></a>

在优化Linux私有镜像过程中，需要在云服务器上修改grub文件磁盘标识方式为UUID。

修改menu.lst或者grub.cfg配置（“/boot/grub/menu.lst”或“/boot/grub/grub.cfg”或“/boot/gurb2/grub.cfg或“/boot/grub/grub.conf”，具体路径根据OS不同会有所不同），启动分区使用UUID方式配置。

>![](public_sys-resources/icon-note.gif) **说明：**   
>根据OS不同，配置文件里标记的root分区会有所不同，可能是“root=/dev/xvda”或“root=/dev/disk”，都需要将grub文件磁盘标识方式修改为UUID的形式。  

## 操作步骤<a name="section6086543611331"></a>

1.  以Ubuntu14.04为例，执行**blkid**命令获取root分区分区对应的UUID并记录下来，编辑/boot/grub/grub.cfg文件，使用root分区的UUID来配置boot项。如果root分区已经使用UUID形式则不需要修改。具体操作方法如下：
    1.  使用root用户登录弹性云服务器。
    2.  执行以下命令，列出当前系统中所有已挂载文件系统的类型以及对应设备的UUID 。

        **blkid**

        回显信息如下所示。

        ```
        /dev/xvda1: UUID="ec51d860-34bf-4374-ad46-a0c3e337fd34” TYPE="ext3"
        /dev/xvda5: UUID="7a44a9ce-9281-4740-b95f-c8de33ae5c11" TYPE="swap"
        ```


    1.  执行以下命令，查看“grub.cfg”文件：

        **cat /boot/grub/grub.cfg**

        回显信息如下所示。：

        ```
        ……menuentry 'Ubuntu Linux, with Linux 3.13.0-24-generic' --class ubuntu --class gnu-linux --class gnu --class os --unrestricted $menuentry_id_option 'gnulinux-3.13.0-24-generic-advanced-ec51d860-34bf-4374-ad46-a0c3e337fd34' {
        recordfail
        load_video
        gfxmode $linux_gfx_mode
        insmod gzio
        insmod part_msdos
        insmod ext2
        if [ x$feature_platform_search_hint = xy ]; then
        search --no-floppy --fs-uuid --set=root ec51d860-34bf-4374-ad46-a0c3e337fd34
        else
        search --no-floppy --fs-uuid --set=root ec51d860-34bf-4374-ad46-a0c3e337fd34
        fi
        echo ‘Loading Linux 3.13.0-24-generic ...’
        linux /boot/vmlinuz-3.13.0-24-generic root=/dev/xvda1 ro 
        echo ‘Loading initial ramdisk ...’
        initrd /boot/initrd.img-3.13.0-24-generic 
        }
        ```


    1.  根据“/boot/grub/grub.cfg”配置文件里标记的root分区，查找是否包括“root=/dev/xvda1”或者“root=UUID=ec51d860-34bf-4374-ad46-a0c3e337fd34”信息。
        -   存在“root=UUID=ec51d860-34bf-4374-ad46-a0c3e337fd34”，即root分区以UUID的表示形式，无需修改。
        -   存在“root=/dev/xvda1”，即root分区以设备名称表示的形式，请执行步骤[1.e](#zh-cn_topic_0037352187_li5200232314010)。


    1.  <a name="zh-cn_topic_0037352187_li5200232314010"></a>根据“root=/dev/xvda1”，即root分区对应的设备名称，以及blkid命令获取的分区信息，找到root分区设备名称对应的UUID。
    2.  执行以下命令，打开“grub.cfg”文件。

        **vi /boot/grub/grub.cfg**

    3.  按“i”进入编辑模式，将root分区改成UUID形式，本例中将“root=/dev/xvda1”修改为“root=UUID=ec51d860-34bf-4374-ad46-a0c3e337fd34”。
    4.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出vi编辑器。
    5.  执行以下命令，确认修改结果。

        **cat /boot/grub/grub.cfg**

        回显信息如下所示表示修改成功，即root分区以UUID的形式表示。

        ```
        ……menuentry 'Ubuntu Linux, with Linux 3.13.0-24-generic' --class ubuntu --class gnu-linux --class gnu --class os --unrestricted $menuentry_id_option 'gnulinux-3.13.0-24-generic-advanced-ec51d860-34bf-4374-ad46-a0c3e337fd34' {
        recordfail
        load_video
        gfxmode $linux_gfx_mode
        insmod gzio
        insmod part_msdos
        insmod ext2
        if [ x$feature_platform_search_hint = xy ]; then
        search --no-floppy --fs-uuid --set=root ec51d860-34bf-4374-ad46-a0c3e337fd34
        else
        search --no-floppy --fs-uuid --set=root ec51d860-34bf-4374-ad46-a0c3e337fd34
        fi
        echo ‘Loading Linux 3.13.0-24-generic ...’
        linux /boot/vmlinuz-3.13.0-24-generic root=UUID=ec51d860-34bf-4374-ad46-a0c3e337fd34 ro
        echo ‘Loading initial ramdisk ...’
        initrd /boot/initrd.img-3.13.0-24-generic
        }
        ```


2.  以CentOS6.5为例，执行**blkid**命令获取root分区对应的UUID并记录下来，编辑“/boot/grub/grub.conf”文件，使用root分区的UUID来配置boot项。如果root分区已经使用UUID形式则不需要修改。具体操作步骤如下：
    1.  使用root用户登录弹性云服务器。
    2.  执行以下命令，列出当前系统中所有已挂载文件系统的类型以及对应设备的UUID 。

        **blkid**

        回显信息如下所示

        ```
        /dev/xvda1: UUID="749d6c0c-990a-4661-bed1-46769388365a" TYPE="swap"  
        /dev/xvda2: UUID="f382872b-eda6-43df-9516-5a687fecdce6" TYPE="ext4"
        ```


    1.  执行以下命令查看“grub.conf”文件：

        **cat /boot/grub/grub.conf**

        回显信息如下所示。

        ```
        default=0 
        timeout=5 
        splashimage=(hd0,1)/boot/grub/splash.xpm.gz 
        hiddenmenu 
        title CentOS (2.6.32-573.8.1.el6.x86_64) 
        root (hd0,1) 
        kernel /boot/vmlinuz-2.6.32-573.8.1.el6.x86_64 ro root=/dev/xvda2 rd_NO_LUKS rd_NO_LVM LANG=en_US.UTF-8 rd_NO_MD SYSFONT=latarcyrheb-sun16 crashkernel=autoKEYBOARDTYPE=pc KEYTABLE=us rd_NO_DM rhgb quiet 
        initrd /boot/initramfs-2.6.32-573.8.1.el6.x86_64.img
        ```


    1.  根据“/boot/grub/grub.conf”配置文件里标记的root分区，查找是否包括“root=/dev/xvda2”或者“root=UUID=f382872b-eda6-43df-9516-5a687fecdce6”信息。
        -   若存在“root=UUID=f382872b-eda6-43df-9516-5a687fecdce6”，即root分区以UUID的表示形式，则无需修改。
        -   若存在“root=/dev/xvda2”，即root分区以设备名称表示的形式，请执行步骤[2.e](#zh-cn_topic_0037352187_li954614614457)。


    1.  <a name="zh-cn_topic_0037352187_li954614614457"></a>根据“root=/dev/xvda2”，即root分区对应的设备名称，以及**blkid**命令获取的分区信息，找到root分区设备名称对应的UUID。
    2.  执行以下命令，打开“grub.conf”文件。

        **vi /boot/grub/grub.conf**

    3.  按“i”进入编辑模式，将root分区改成UUID形式，本例中将“root=/dev/xvda2”修改为“root=UUID=f382872b-eda6-43df-9516-5a687fecdce6”。
    4.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出vi编辑器。
    5.  修改后，执行以下命令确认修改结果。

        **cat /boot/grub/grub.cfg**

        回显信息如下所示表示修改成功，即root分区以UUID的形式表示。

        ```
        default=0 
        timeout=5 
        splashimage=(hd0,1)/boot/grub/splash.xpm.gz 
        hiddenmenu 
        title CentOS (2.6.32-573.8.1.el6.x86_64) 
        root (hd0,1) 
        kernel /boot/vmlinuz-2.6.32-573.8.1.el6.x86_64 ro root=UUID=f382872b-eda6-43df-9516-5a687fecdce6 rd_NO_LUKS rd_NO_LVM LANG=en_US.UTF-8 rd_NO_MD SYSFONT=latarcyrheb-sun16 crashkernel=autoKEYBOARDTYPE=pc KEYTABLE=us rd_NO_DM rhgb quiet 
        initrd /boot/initramfs-2.6.32-573.8.1.el6.x86_64.img
        ```


3.  以CentOS7.0为例，执行**blkid**命令获取root分区分区对应的UUID并记录下来，编辑“/boot/grub2/grub.cfg”文件，使用root分区的UUID来配置boot项。如果root分区已经使用UUID形式则不需要修改。
    1.  使用root用户登录弹性云服务器。
    2.  执行以下命令，列出当前系统中所有已挂载文件系统的类型以及对应设备的UUID 。

        **blkid**

        回显信息如下所示。****

        ```
        /dev/xvda2: UUID="4eb40294-4c6f-4384-bbb6-b8795bbb1130" TYPE="xfs"  
        /dev/xvda1: UUID="2de37c6b-2648-43b4-a4f5-40162154e135" TYPE="swap" 
        ```


    1.  执行以下命令查看“grub.cfg”文件：

        **cat /boot/grub2/grub.cfg**

        回显信息如下所示。

        ```
        …… 
        menuentry 'Red Hat Enterprise Linux Server 7.1 (Maipo), with Linux 3.10.0-229.el7.x86_64' --class fedora --class gnu-linux --class gnu --class os --unrestricted $menuentry_id_option 'gnulinux-3.10.0-229.el7.x86_64-advanced-4eb40294-4c6f-4384-bbb6-b8795bbb1130' { 
        load_video 
        set gfxpayload=keep 
        insmod gzio 
        insmod part_msdos 
        insmod xfs 
        set root='hd0,msdos2' 
        if [ x$feature_platform_search_hint = xy ]; then 
        search --no-floppy --fs-uuid --set=root --hint='hd0,msdos2'4eb40294-4c6f-4384-bbb6-b8795bbb1130 
        else 
        search --no-floppy --fs-uuid --set=root 4eb40294-4c6f-4384-bbb6-b8795bbb1130 
        fi 
        linux16 /boot/vmlinuz-3.10.0-229.el7.x86_64 root=/dev/xvda2 ro crashkernel=auto rhgb quiet LANG=en_US.UTF-8 
        initrd16 /boot/initramfs-3.10.0-229.el7.x86_64.img 
        }
        ```


    1.  根据“/boot/grub/grub.cfg”配置文件里标记的root分区，查找是否包括root=/dev/xvda2或者包括root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130信息。
        -   存在“root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130”，即root分区以UUID的表示形式，则无需修改。
        -   存在“root=/dev/xvda2”，即root分区以设备名称表示的形式，请执行步骤[3.e](#zh-cn_topic_0037352187_li2365474142222)。


    1.  <a name="zh-cn_topic_0037352187_li2365474142222"></a>根据“root=/dev/xvda2”，即root分区对应的设备名称，以及**blkid**命令获取的分区信息，找到root分区设备名称对应的UUID。
    2.  执行以下命令，打开“grub.cfg”文件。

        **vi /boot/grub2/grub.cfg**

    3.  按“i”进入编辑模式，将root分区改成UUID形式，本例中将“root=/dev/xvda2”修改为“root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130”。
    4.  按“Esc”后，输入“:wq”，按“Enter”。 保存设置并退出vi编辑器。
    5.  执行以下命令确认修改结果。

        **cat /boot/grub2/grub.cfg**

        回显信息如下所示表示修改成功，即root分区以UUID的形式表示。

        ```
        …… 
        menuentry 'Red Hat Enterprise Linux Server 7.1 (Maipo), with Linux 3.10.0-229.el7.x86_64' --class fedora --class gnu-linux --class gnu --class os --unrestricted $menuentry_id_option 'gnulinux-3.10.0-229.el7.x86_64-advanced-4eb40294-4c6f-4384-bbb6-b8795bbb1130' { 
        load_video 
        set gfxpayload=keep 
        insmod gzio 
        insmod part_msdos 
        insmod xfs 
        set root='hd0,msdos2' 
        if [ x$feature_platform_search_hint = xy ]; then 
        search --no-floppy --fs-uuid --set=root --hint='hd0,msdos2'4eb40294-4c6f-4384-bbb6-b8795bbb1130 
        else 
        search --no-floppy --fs-uuid --set=root 4eb40294-4c6f-4384-bbb6-b8795bbb1130 
        fi 
        linux16 /boot/vmlinuz-3.10.0-229.el7.x86_64 root=UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130 ro crashkernel=auto rhgb quiet LANG=en_US.UTF-8 
        initrd16 /boot/initramfs-3.10.0-229.el7.x86_64.img 
        }
        ```



