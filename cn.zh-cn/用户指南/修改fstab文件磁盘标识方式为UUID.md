# 修改fstab文件磁盘标识方式为UUID<a name="ims_01_0325"></a>

## 操作场景<a name="section2074321418513"></a>

在优化Linux私有镜像过程中，需要在云服务器上修改fstab文件磁盘标识方式为UUID。

## 操作步骤<a name="section60166277114746"></a>

-   以CentOS 7.0为例，执行**blkid**命令获取所有分区对应的UUID并记录下来，编辑“/etc/fstab”文件，使用分区的UUID来配置分区自动挂载。

1.  使用root用户登录云服务器。
2.  执行以下命令，列出当前系统中所有已挂载文件系统的类型以及对应设备的UUID 。

    **blkid**

    回显信息如下所示。

    ```
    /dev/xvda2: UUID="4eb40294-4c6f-4384-bbb6-b8795bbb1130" TYPE="xfs"  
    /dev/xvda1: UUID="2de37c6b-2648-43b4-a4f5-40162154e135" TYPE="swap"
    ```

3.  执行以下命令，查看“fstab”文件。

    **cat /etc/fstab**

    回显信息如下所示。

    ```
    [root@CTU1000028010 ~]# cat /etc/fstab  
    /dev/xvda2  /       xfs     defaults    0 0 
    /dev/xvda1  swap    swap    defaults    0 0     
    ```

4.  查看“fstab”文件中的磁盘的表示形式为设备名称。
    -   若为UUID的表示形式，无需修改。
    -   若为设备名称的表示形式，请执行步骤[5](#li63646666154817)。

5.  <a name="li63646666154817"></a>执行以下命令，打开“fstab”文件。

    **vi /etc/fstab**

6.  按“i”进入编辑模式，将fstab中的磁盘表示形式修改为UUID的形式。

-   以CentOS 7.1为例，执行**blkid**命令获取所有分区对应的UUID并记录下来，编辑“/etc/fstab”文件，使用分区的UUID来配置分区自动挂载。

1.  使用root用户登录云服务器。
2.  执行以下命令，列出当前系统中所有已挂载文件系统的类型以及对应设备的UUID 。

    **blkid**

    ```
    /dev/xvda2: UUID="4eb40294-4c6f-4384-bbb6-b8795bbb1130" TYPE="xfs" 
    /dev/xvda1: UUID="2de37c6b-2648-43b4-a4f5-40162154e135" TYPE="swap"
    ```

    修改前：

    ```
    [root@CTU1000028010 ~]# cat /etc/fstab 
    /dev/xvda2  /       xfs     defaults    0 0
    /dev/xvda1  swap    swap    defaults    0 0
    ```

    修改后：

    ```
    [root@CTU1000028010 ~]# cat /etc/fstab 
    UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130  /       xfs     defaults    0 0
    UUID=2de37c6b-2648-43b4-a4f5-40162154e135  swap    swap    defaults    0 0
    ```

3.  按“Esc”后，输入**:wq**，按“Enter”。 保存设置并退出vi编辑器。
4.  修改后，执行以下命令确认修改结果。

    **cat /etc/fstab**

    回显信息如下所示，即磁盘的表示形式为UUID，表示修改成功。

    ```
    [root@CTU1000028010 ~]# cat /etc/fstab  
    UUID=4eb40294-4c6f-4384-bbb6-b8795bbb1130  /       xfs     defaults    0 0 
    UUID=2de37c6b-2648-43b4-a4f5-40162154e135  swap    swap    defaults    0 0     
    ```


