# 查看Windows操作系统云服务器虚拟化类型<a name="ims_01_0316"></a>

您可以在cmd窗口输入以下命令，查看当前云服务器的虚拟化类型。

**systeminfo**

查看回显信息中System Manufacturer和BIOS版本显示为XEN，说明当前云服务器为XEN虚拟化类型，如果需要同时支持KVM虚拟化，请参考本章节操作优化Windows私有镜像。

>![](public_sys-resources/icon-note.gif) **说明：**   
>如果查出来的虚拟化类型为KVM，也建议您优化私有镜像，避免最终发放的云服务器出现一些不可预知的异常。  

**图 1**  查看Windows云服务器虚拟化类型<a name="fig167731211184410"></a>  
![](figures/查看Windows云服务器虚拟化类型.png "查看Windows云服务器虚拟化类型")

