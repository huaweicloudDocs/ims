# 安装Guest OS driver到Windows云服务器<a name="ZH-CN_TOPIC_0030713187"></a>

使用镜像文件创建私有镜像时，需要安装云平台提供的Guest OS driver才能保证云服务器正常运行。

## 操作场景<a name="zh-cn_topic_0029124549_section20599159151631"></a>

云服务器的正常运行依赖于XEN Guest OS driver（PV driver）和KVM Guest OS driver（UVP VMTools），因此，在云平台使用镜像文件创建私有镜像时，需要安装云平台提供的Guest OS driver。未安装会对云服务器运行时的性能产生影响，云服务器的部分功能会有缺失。注册的私有镜像为Windows操作系统时，必须安装Guest OS driver。

用户可以下载Guest OS driver安装包并通过RDP上传安装包到云服务器中，或者在云服务器中直接下载安装包。

本节以上传Guest OS driver安装包到云服务器为例，介绍如何安装Guest OS driver到Windows服务器。

## 前提条件<a name="zh-cn_topic_0029124549_section4184671115244"></a>

-   已确保Windows云服务器网卡设置为DHCP的方式动态获取网络地址。
-   已启用Windows云服务器的RDP协议。
-   已安装Cloudbase-init工具并进行了相关配置。

## 操作步骤<a name="zh-cn_topic_0029124549_section42330456151542"></a>

1.  为了避免在云服务器上安Guest OS driver失败，安装前需要先卸载第三方虚拟化平台的工具（例如，Citrix Xen Tools、VMware Tools）。相关卸载方法请参考对应的工具的官方文档。
2.  安装PV driver。

    具体操作请参考[在Windows系统中安装PV driver](在Windows系统中安装PV-driver.md)。

3.  安装UVP VMTools。

    具体操作请参考[Windows上安装UVP VMTools](Windows上安装UVP-VMTools.md)。



