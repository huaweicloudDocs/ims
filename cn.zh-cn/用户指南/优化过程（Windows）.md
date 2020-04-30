# 优化过程（Windows）<a name="zh-cn_topic_0047501112"></a>

云服务器的正常运行依赖于XEN Guest OS driver（PV driver）和KVM Guest OS driver（UVP VMTools），为了同时支持XEN虚拟化和KVM虚拟化，以及提升云服务器网络性能，需要确保镜像安装了PV driver和UVP VMTools。

1.  将待优化的Windows私有镜像创建为云服务器，并开机登录该云服务器。
2.  在云服务器上安装最新版本PV driver。

    具体操作请参见[安装PV driver](安装PV-driver.md)。

3.  安装在KVM虚拟化资源池创建云服务器所需的UVP VMTools。

    具体操作请参见[安装UVP VMTools](安装UVP-VMTools.md)。

4.  在云服务器操作系统中打开“控制面板 \> 电源选项”，在左侧单击“选择关闭显示器的时间”，将“关闭显示器”设置为“从不”，然后保存修改。
5.  清除系统日志，然后关闭云服务器。

    具体操作请参见[清除系统日志](清除系统日志.md)。

6.  通过云服务器创建Windows私有镜像。

