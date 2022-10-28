# 配置云服务器并创建Windows系统盘镜像<a name="ims_01_0225"></a>

## 操作场景<a name="section0252194914911"></a>

安装完操作系统后的临时云服务器还需要进行相关配置，并安装云平台提供的Guest OS driver，才能保证后续创建的云服务器正常使用。

>![](public_sys-resources/icon-note.gif) **说明：** 
>Guest OS driver包括VMTools驱动和PV driver，在前面步骤中已为云服务器安装VMTools驱动，因此本节只需要安装PV driver即可。

该任务指导用户完成Windows云服务器的相关配置与驱动安装，从而创建为Windows系统盘镜像。

## 操作步骤<a name="section390891419109"></a>

1.  配置云服务器。
    1.  检查网卡属性是否为DHCP。如果云服务器网络配置为静态IP地址，请参考“[设置网卡属性为DHCP](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030713152.html)”修改为DHCP方式。
    2.  对于需要使用Windows远程桌面连接方式进行访问的云服务器，需要开启远程桌面连接功能，请参考“[开启远程桌面连接功能](https://support.huaweicloud.com/usermanual-ims/ims_01_0401.html)”。
    3.  安装PV driver，请参考“[安装PV driver](https://support.huaweicloud.com/usermanual-ims/ims_01_0318.html)”。

        安装完以后需要清除系统日志，请参考“[清除系统日志](https://support.huaweicloud.com/usermanual-ims/ims_01_0320.html)”。

    4.  安装并配置Cloudbase-Init，保证镜像创建的新云服务器可以使用控制台的“用户数据注入”功能注入初始化自定义信息（例如为云服务器设置登录密码）。请参考“[安装并配置Cloudbase-Init工具](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030730602.html)”。
    5.  （可选）配置增值功能。
        -   开启网卡多队列，请参考“[如何设置镜像的网卡多队列属性？](https://support.huaweicloud.com/ims_faq/ims_faq_0030.html)”。
        -   配置IPv6地址，请参考“[如何开启云服务器动态获取IPv6（试用）？](https://support.huaweicloud.com/ims_faq/ims_faq_0046.html)”。

2.  关机云服务器，使上述配置生效。
3.  创建Windows系统盘镜像。

    具体操作请参考[通过云服务器创建Windows系统盘镜像](通过云服务器创建Windows系统盘镜像.md)。


## 后续操作<a name="section14462447154515"></a>

系统盘镜像创建成功后，请及时删除临时云服务器，避免继续产生费用。

