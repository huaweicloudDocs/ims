# 使用ISO镜像创建Windows云服务器<a name="ims_01_0223"></a>

## 操作场景<a name="section91420278141"></a>

该任务指导用户使用已注册成功的ISO镜像创建弹性云服务器。

## 约束与限制<a name="section22091213103516"></a>

暂不支持专属云用户通过ISO镜像创建弹性云服务器。

## 操作步骤<a name="section2598639141418"></a>

1.  登录IMS控制台。
    1.  登录管理控制台。
    2.  选择“计算 \> 镜像服务”。

        进入镜像服务页面。

2.  创建弹性云服务器。
    1.  单击“私有镜像”页签，在ISO镜像所在行的“操作”列下，单击“安装服务器”，创建云服务器。

        由于此云服务器仅作为临时云服务器使用，最终需要删除。因此，系统会默认创建一个固定规格且“按需付费”的云服务器，使用该云服务器创建的私有镜像再次创建云服务器时不会限制规格和付费方式。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >对于专属云用户，不支持使用ISO镜像创建临时云服务器操作，此时“安装服务器”按钮灰化。

    2.  根据界面提示完成云服务器的配置，并单击“确定”。

        **图 1**  安装弹性云服务器<a name="fig61088361547"></a>  
        ![](figures/安装弹性云服务器.png "安装弹性云服务器")



## 后续操作<a name="section163620465618"></a>

弹性云服务器创建成功后，使用平台提供的“远程登录”方式，登录弹性云服务器，继续执行后续的安装操作系统和相关驱动操作。

