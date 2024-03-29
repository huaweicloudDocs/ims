# 安装并配置Cloudbase-Init工具<a name="zh-cn_topic_0030730602"></a>

## 操作场景<a name="zh-cn_topic_0029124575_section21661076191949"></a>

为了保证使用私有镜像创建的新云服务器可以通过“用户数据注入”功能注入初始化自定义信息（例如为云服务器设置登录密码），建议您在创建私有镜像前安装Cloudbase-Init工具。

-   不安装Cloudbase-Init工具，将无法对云服务器进行自定义配置，只能使用镜像原有密码登录云服务器。
-   使用公共镜像创建的云服务器，默认已经安装Cloudbase-Init，不需要执行安装及配置操作。
-   使用外部镜像文件创建的云服务器，请按照指导安装及配置Cloudbase-Init。

## 前提条件<a name="zh-cn_topic_0029124575_section31429961161037"></a>

-   已为云服务器绑定弹性公网IP。
-   已登录到云服务器。
-   云服务器的网卡属性为DHCP方式。
-   已安装一键式重置密码插件。

    因为安装Cloudbase-Init工具的操作步骤中如果有重启云服务器的操作，可能导致密码被修改为一个随机密码，所以需要安装一键式重置密码插件重置密码。操作步骤请参考[安装一键式重置密码插件（Windows）](安装一键式重置密码插件（Windows）.md)。


## 安装Cloudbase-Init工具<a name="zh-cn_topic_0029124575_section54473519191017"></a>

1.  在Windows操作系统中，单击“开始”，选择“控制面板 \> 程序 \> 程序和功能”查看是否安装Cloudbase-Init。
    -   是，无需重复安装，直接执行[配置Cloudbase-Init工具](#section67455211370)。
    -   否，执行以下安装操作步骤。

2.  操作系统是否为Windows桌面版。
    -   是，执行[3](#li5127112791712)。
    -   否，若操作系统为Windows Server版本，请执行[4](#zh-cn_topic_0029124575_li6098361192920)。

3.  <a name="li5127112791712"></a>如果操作系统是Windows桌面版，如Windows 7或者Windows 10，那么需要在安装Cloudbase-Init前确保Adminstrator帐号未禁用。以Windows 7为例，具体操作请以实际为准。
    1.  在操作系统中单击“开始”，选择的“控制面板 \> 系统和安全 \> 管理工具”。
    2.  双击“计算机管理”。
    3.  选择“系统工具 \> 本地用户和组 \> 用户”。
    4.  右键单击“Administrator”，选择“属性”。
    5.  确认已取消勾选“帐户已禁用”选项。

4.  <a name="zh-cn_topic_0029124575_li6098361192920"></a>下载Cloudbase-Init工具安装包。

    根据Windows操作系统的不同位数，您需要下载不同版本的Cloudbase-Init工具安装包。Cloudbase官网：[http://www.cloudbase.it/cloud-init-for-windows-instances/](http://www.cloudbase.it/cloud-init-for-windows-instances/)。

    Cloudbase-Init分为稳定版本和Beta版本两种。

    稳定版本获取路径：

    -   64位：[https://www.cloudbase.it/downloads/CloudbaseInitSetup\_Stable\_x64.msi](https://www.cloudbase.it/downloads/CloudbaseInitSetup_Stable_x64.msi)
    -   32位：[https://www.cloudbase.it/downloads/CloudbaseInitSetup\_Stable\_x86.msi](https://www.cloudbase.it/downloads/CloudbaseInitSetup_Stable_x86.msi)

    Beta版本获取路径：

    -   64位：[https://www.cloudbase.it/downloads/CloudbaseInitSetup\_x64.msi](https://www.cloudbase.it/downloads/CloudbaseInitSetup_x64.msi)
    -   32位：[https://www.cloudbase.it/downloads/CloudbaseInitSetup\_x86.msi](https://www.cloudbase.it/downloads/CloudbaseInitSetup_x86.msi)

5.  打开Cloudbase-Init工具安装包开始安装。
6.  单击“Next”。
7.  勾选“I accept the terms in the License Agreement”，单击“Next”。
8.  使用Cloudbase-Init默认安装路径进行安装，单击“Next”。
9.  在“Configuration options”窗口中，设置用户名为“Administrator”，日志输出串口选择“COM1”，且不勾选“Run Cloudbase-Init service as LocalSystem”。如[图1](#fig416499174516)所示。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >图片中的版本号仅供参考，请以实际情况为准。

    **图 1**  设置参数<a name="fig416499174516"></a>  
    ![](figures/设置参数.png "设置参数")

10. 单击“Next”。
11. 单击“Install”。
12. 在“Files in Use”窗口保留默认勾选“Close the application and attempt to restart them”，单击“OK”。
13. 操作系统是否为Windows桌面版。
    -   是，执行[15](#li8450150161333)。
    -   否，执行[14](#li208441311639)。

14. <a name="li208441311639"></a>在“Completed the Cloudbase-Init Setup Wizard ”窗口，请勿勾选“Run Sysprep to create a generalized Image. This is necessary if you plan to duplicate this instance, for example by creating a Glance image”及“Shutdown when Sysprep terminate”。如[图2](#fig515010583213)所示。

    **图 2**  完成安装<a name="fig515010583213"></a>  
    ![](figures/完成安装.png "完成安装")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >图片中的版本号仅供参考，请以实际情况为准。

15. <a name="li8450150161333"></a>单击“Finish”。

## 配置Cloudbase-Init工具<a name="section67455211370"></a>

1.  在Cloudbase-Init安装路径下的配置文件“C:\\Program Files\\Cloudbase Solutions\\Cloudbase-Init\\conf\\cloudbase-init.conf”中执行以下操作：
    1.  在配置文件最后一行，增加配置项“netbios\_host\_name\_compatibility=false”，使Windows系统的hostname长度支持到63个字符。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >NetBIOS长度受Windows系统本身的限制还只支持小于等于15个字符。

    2.  增加配置项“metadata\_services=cloudbaseinit.metadata.services.httpservice.HttpService”，配置agent访问OpenStack数据源。
    3.  **（可选）**增加如下配置项，配置获取metadata的重试次数和间隔。

        ```
        retry_count=40
        retry_count_interval=5
        ```

    4.  **（可选）**增加如下配置项，防止Windows添加默认路由导致metadata网络不通。

        ```
        [openstack]
        add_metadata_private_ip_route=False
        ```

    5.  **（可选）**当Cloudbase-Init为0.9.12及以上版本时，用户可以自定义配置密码长度。

        操作方法：修改配置项“user\_password\_length”的值，完成密码长度的自定义配置。

    6.  **（可选）**选择密码注入方式首次登录时，系统默认强制用户修改登录密码，若用户根据个人意愿，不需要修改首次登录使用的密码时，可关闭此功能。

        操作方法：增加配置项“first\_logon\_behaviour=no”。

2.  为了防止镜像中DHCP租期过长导致创建的云服务器无法正确的获取地址，用户需要释放当前的DHCP地址。

    在Windows命令行中，执行以下命令释放当前的DHCP地址。

    **ipconfig /release**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >此操作会中断网络，对云服务器的使用会产生影响。当云服务器再次开机后，网络会自动恢复。

3.  使用Windows操作系统云服务器制作镜像时，需修改云服务器SAN策略为OnlineAll类型。否则可能导致使用镜像创建云服务器时磁盘处于脱机状态。

    Windows操作系统SAN策略分为三种类型：OnlineAll、OfflineShared、OfflineInternal

    **表 1**  Windows操作系统SAN策略类型

|类型|说明|
|--|--|
|OnlineAll|表示所有新发现磁盘都置于在线模式。|
|OfflineShared|表示所有共享总线上（比如FC、ISCSI）的新发现磁盘都置于离线模式，非共享总线上的磁盘都置于在线模式。|
|OfflineInternal|表示所有新发现磁盘都置于离线模式。|


    1.  运行cmd.exe，执行以下命令，使用DiskPart工具来查询云服务器当前的SAN策略。

        **diskpart**

    2.  执行以下命令查看云服务器当前的SAN策略。

        **san**

        -   如果SAN策略为OnlineAll，请执行**exit**命令退出DiskPart。

        -   否，请执行步骤[3.c](#li1823793883810)。

    3.  <a name="li1823793883810"></a>执行以下命令修改云服务器SAN策略为OnlineAll。

        **san policy=onlineall**



