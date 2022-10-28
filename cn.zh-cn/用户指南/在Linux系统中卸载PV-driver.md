# 在Linux系统中卸载PV driver<a name="ims_01_0323"></a>

## 操作场景<a name="section8801182220417"></a>

在优化Linux私有镜像过程中，需要在云服务器上修改fstab和grub的UUID，并安装原生的XEN和KVM驱动。为了成功安装原生的XEN和KVM驱动，需要先卸载PV driver。

## 操作步骤<a name="section1381148120949"></a>

1.  使用VNC方式，以“root”用户登录云服务器。
2.  执行如下命令，检查操作系统中是否安装PV driver相关的驱动。

    **ps -ef | grep uvp-monitor**

    -   若回显信息如下所示，表示已安装PV driver相关的驱动。
    -   若无如下回显信息，表示未安装PV driver相关的驱动，本节操作结束。

    ```
    root     4561        1    0   Jun29 ?           00:00:00   /usr/bin/uvp-monitor
    root     4567     4561    0   Jun29 ?           00:00:00   /usr/bin/uvp-monitor
    root     6185     6085    0   03:04  pts/2      00:00:00   grep uvp-monitor
    ```

3.  在VNC登录窗口的云服务器操作系统界面，打开命令行终端（具体方式请查询对应操作系统的使用手册）。

    进入命令行模式。

4.  执行以下命令，卸载PV driver。

    **/etc/.uvp-monitor/uninstall**

    -   回显信息如下时，表示Tools卸载成功。

        ```
        The PV driver is uninstalled successfully. Reboot the system for the uninstallation to take effect.
        ```

    -   回显信息如下提示不存在“.uvp-monitor”时，请执行步骤[5](#li45681026173616)。

        ```
        -bash: /etc/.uvp-monitor/uninstall: No such file or directory
        ```

5.  <a name="li45681026173616"></a>执行如下操作，删除KVM虚拟化平台下不生效的uvp-monitor，防止日志溢出。
    1.  执行如下命令，查询操作系统是否安装了UVP用户态相关的监控程序。

        **rpm -qa | grep uvp**

        回显信息如下所示：

        ```
        libxenstore_uvp3_0-3.00-36.1.x86_64
        uvp-monitor-2.2.0.315-3.1.x86_64
        kmod-uvpmod-2.2.0.315-3.1.x86_64
        ```

    2.  执行如下命令，删除以下三个安装包。

        **rpm -e kmod-uvpmod**

        **rpm -e uvp-monitor**

        **rpm -e libxenstore\_uvp**



