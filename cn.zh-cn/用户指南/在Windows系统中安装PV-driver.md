# 在Windows系统中安装PV driver<a name="ZH-CN_TOPIC_0037352182"></a>

## 操作场景<a name="section854616214319"></a>

弹性云服务器创建并安装操作系统后创建镜像时，可在弹性云服务器上安装PV driver，以便提高弹性云服务器的I/O处理性能、实现对云服务器硬件的监控和其他高级功能。

执行如下命令，检查操作系统中安装的 PV driver的版本信息。

**C:\\Program Files \(x86\)\\Xen PV Drivers\\bin\\version**

**pvdriverVersion=3.0.36.61**

-   如果PV driver的版本高于2.3版本，执行[Windows上安装UVP VMTools](Windows上安装UVP-VMTools.md)。
-   如果PV driver的版本低于或等于2.3版本，执行[安装PV Driver](#zh-cn_topic_0036684067_section46181951)或[安装PV Driver升级包](#section14208143620187)。

## 前提条件<a name="zh-cn_topic_0036684067_section34957489"></a>

-   弹性云服务器已安装操作系统，弹性云服务器已经绑定弹性IP。
-   弹性云服务器的系统磁盘的剩余空间必须大于32MB。
-   如果弹性云服务器的操作系统为Windows 2008需使用Administrator用户安装 PV driver。
-   弹性云服务器已下载 PV driver软件包。软件包获取请参考[相关软件及获取方式](相关软件及获取方式.md)。

## 安装PV Driver<a name="zh-cn_topic_0036684067_section46181951"></a>

1.  VNC登录Windows弹性云服务器。

    登录云服务器的相关操作请参见《弹性云服务器用户指南》。

2.  在云服务器操作系统界面，选择“开始 \> 控制面板”。
3.  单击“卸载程序”。
4.  按照提示，卸载“GPL PV Drivers for Windows x.x.x.xx”。
5.  根据[相关软件及获取方式](相关软件及获取方式.md)和弹性云服务器的操作系统类型下载对应的PV driver版本。
6.  解压PV driver软件包。
7.  右键单击“GPL PV Drivers for Windows x.x.x.xx”，并选择“以管理员身份运行”，根据界面提示完成安装。
8.  根据提示重启云服务器，使PV driver生效。

    对于Windows Server2008系统的云服务器，必须重启两次。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >安装PV driver后，云服务器网卡的配置信息会丢失，因此，若之前已配置网卡，需重新配置网卡信息。  


## 安装PV Driver升级包<a name="section14208143620187"></a>

1.  VNC登录Windows弹性云服务器。

    登录云服务器的相关操作请参见《弹性云服务器用户指南》。

2.  在云服务器操作系统界面，选择“开始 \> 控制面板”。
3.  单击“卸载程序”。
4.  按照提示，卸载“GPL PV Drivers for Windows x.x.x.xx”。
5.  下载pvdriver-windows.zip升级包。

    下载地址：[https://ecs-instance-driver.obs.myhwclouds.com/pvdriver-windows.zip](https://ecs-instance-driver.obs.myhwclouds.com/pvdriver-windows.zip)

6.  解压pvdriver-windows.zip升级包。
7.  单击setup.exe完成升级安装，且pvdriver-windows升级包会自动匹配当前操作系统版本。
8.  根据提示重启云服务器，使PV driver生效。

    对于Windows Server2008系统的云服务器，必须重启两次。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >安装PV driver后，云服务器网卡的配置信息会丢失，因此，若之前已配置网卡，需重新配置网卡信息。  


