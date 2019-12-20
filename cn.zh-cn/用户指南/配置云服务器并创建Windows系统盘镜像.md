# 配置云服务器并创建Windows系统盘镜像<a name="ims_01_0225"></a>

## 操作场景<a name="section0252194914911"></a>

安装完操作系统后的临时云服务器还需要进行相关配置，并安装云平台提供的Guest OS driver，才能保证后续创建的云服务器正常使用。

>![](public_sys-resources/icon-note.gif) **说明：**   
>Guest OS driver包括VMTools驱动和PV driver，在前面步骤中已为云服务器安装VMTools驱动，因此本节只需要安装PV driver即可。  

该任务指导用户完成Windows云服务器的相关配置与驱动安装，从而创建为Windows系统盘镜像。

## 操作步骤<a name="section390891419109"></a>

1.  配置云服务器。

    具体操作请参考“[Windows外部镜像文件在导出前未完成初始化配置，怎么办？](https://support.huaweicloud.com/ims_faq/ims_faq_0100.html#section1170711344016)”中的“步骤4：配置云服务器”。

2.  创建Windows系统盘镜像。

    具体操作请参考[通过云服务器创建Windows系统盘镜像](通过云服务器创建Windows系统盘镜像.md)。


## 后续处理<a name="section14462447154515"></a>

系统盘镜像创建成功后，请及时删除临时云服务器，避免继续产生费用。

