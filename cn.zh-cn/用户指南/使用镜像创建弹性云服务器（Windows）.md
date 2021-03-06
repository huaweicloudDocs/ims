# 使用镜像创建弹性云服务器（Windows）<a name="ims_01_0207"></a>

## 操作场景<a name="section17191143145412"></a>

将外部镜像文件注册成云平台的私有镜像后，您可以使用该镜像创建新的云服务器，或对已有云服务器的系统进行重装和更换。本节介绍使用镜像创建云服务器的操作。

## 操作步骤<a name="section328511235510"></a>

您可以按照[通过镜像创建云服务器](通过镜像创建云服务器.md)中的操作指导创建弹性云服务器。

在配置参数时，需要注意以下几点：

-   区域：必须选择私有镜像所在的区域。
-   规格：在选择规格时，需要结合镜像的操作系统类型以及“[弹性云服务器类型与支持的操作系统版本](https://support.huaweicloud.com/productdesc-ims/ims_01_0007.html)”了解支持选择的规格范围。
-   镜像：选择“私有镜像”，并在下拉列表中选择所创建的私有镜像。
-   （可选）数据盘：添加数据盘，该数据盘使用随系统盘镜像一起创建出来的数据盘镜像来创建，这样便可以将原平台虚拟机的系统盘和数据盘数据一起迁移到当前云平台。

