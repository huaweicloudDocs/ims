# IMS自定义策略<a name="ims_01_0415"></a>

如果系统预置的IMS权限不满足您的授权要求，可以创建自定义策略。自定义策略中可以添加的授权项（Action）请参考：[策略及授权项说明](https://support.huaweicloud.com/api-ims/zh-cn_topic_0171654733.html)。

目前华为云支持以下两种方式创建自定义策略：

-   可视化视图创建自定义策略：无需了解策略语法，按可视化视图导航栏选择云服务、操作、资源、条件等策略内容，可自动生成策略。
-   JSON视图创建自定义策略：可以在选择策略模板后，根据具体需求编辑策略内容；也可以直接在编辑框内编写JSON格式的策略内容。

具体创建步骤请参见：[创建自定义策略](https://support.huaweicloud.com/usermanual-iam/iam_01_0605.html)。本章为您介绍常用的IMS自定义策略样例。

## 策略样例<a name="section1449217811913"></a>

-   示例1：授权用户制作镜像

    ```
    {
        "Version": "1.1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "ims:serverImages:create",
                    "obs:bucket:*",
                    "obs:object:*",
                    "kms:*:*",
                    "ecs:cloudServers:get",
                    "ecs:servers:get",
                    "ecs:serverVolumes:use",
                    "ecs:cloudServers:list",
                    "ecs:serverVolumeAttachments:list",
                    "ecs:servers:list",
                    "evs:volumes:*",
                    "bms:servers:list",
                    "bms:servers:get",
                    "bms:serverFlavors:get"
                ]
            }
        ]
    }
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >制作镜像对应的授权项为：ims:serverImages:create，其他授权项均为制作镜像所依赖的授权项。  

-   示例2：拒绝用户删除镜像

    拒绝策略需要同时配合其他策略使用，否则没有实际作用。用户被授予的策略中，一个授权项的作用如果同时存在Allow和Deny，则遵循**Deny优先原则**。

    如果您给用户授予IMS Admin的系统策略，但不希望用户拥有IMS Admin中定义的删除镜像权限，您可以创建一条拒绝删除镜像的自定义策略，然后同时将IMS Admin和拒绝策略授予用户，根据Deny优先原则，则用户可以对IMS执行除了删除镜像外的所有操作。拒绝策略示例如下：

    ```
    {
        "Version": "1.1",
        "Statement": [
            {
                "Effect": "Deny",
                "Action": [
                    "ims:images:delete"
                ]
            }
        ]
    }
    ```


