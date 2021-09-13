# 使用ISO文件创建镜像<a name="ims_03_0801"></a>

## 场景描述<a name="zh-cn_topic_0219577800_section770669154912"></a>

ISO是一种光盘映像文件，通过特定的压缩方式，将大量的数据文件统一为一个后缀名为iso的映像文件。ISO文件可以理解为从光盘中复制出来的数据文件，所以ISO文件无法直接使用，需要利用一些工具进行解压后才能使用。例如使用虚拟光驱打开，或者将ISO文件刻录到光盘中后，使用光驱来进行读取。

本章介绍通过ISO文件创建私有镜像的API操作过程。

## 涉及API<a name="zh-cn_topic_0219577800_section88981920144910"></a>

当您使用Token认证方式完成认证鉴权时，需要获取用户Token并在调用接口时增加“X-Auth-Token”到业务接口请求消息头中。

-   IAM获取token的API

    URI格式：POST https://\{IAM的Endpoint\}/v3/auth/tokens

-   镜像服务API：制作镜像（使用上传至OBS桶中的外部镜像文件制作私有镜像）

    URI格式：POST https://\{IMS的Endpoint\}/v2/cloudimages/action

-   弹性云服务器API：创建云服务器（按需）

    URI格式：POST https://\{ECS的Endpoint\}/v1/\{project\_id\}/cloudservers

-   镜像服务API：制作镜像（使用数据卷制作系统盘镜像）

    URI格式：POST https://\{IMS的Endpoint\}/v2/cloudimages/action


## 具体步骤<a name="zh-cn_topic_0219577800_section179364287499"></a>

1.  Token认证，具体操作请参考[认证鉴权](认证鉴权.md)。
2.  使用上传至OBS桶中的ISO镜像文件制作私有镜像。
    1.  发送“POST https://\{IMS的Endpoint\}/v2/cloudimages/action”。
    2.  在Request Header中增加“X-Auth-Token”。
    3.  在Request Body中传入如下参数：

        详细的参数说明请参见“[制作镜像](制作镜像.md#li3688227151754)”。

        ```
        {
            "name": "ims_test_file",  //镜像名称（必填String）
            "description": "OBS文件制作镜像",  //镜像描述（非必填String）
            "image_url": "ims-image:centos70.iso",  //OBS桶中外部镜像文件地址（必填String）
            "os_type": "Linux",  //操作系统类型（非必填String）
            "os_version": "CentOS 7.0 64bit",  //操作系统版本（必填String）
            "type": "IsoImage",  //镜像的类型（必填String）
            "min_disk": 40,  //最小系统盘大小（必填Integer）
            "image_tags": [{"key":"key2","value":"value2"},{"key":"key1","value":"value1"}]  //镜像标签列表（非必填Array of objects）
        }
        ```

    4.  请求响应成功后，返回job\_id，根据job\_id查询job详情，可以获取镜像ID。具体操作请参考[异步任务查询](异步任务查询.md)。

3.  根据ISO镜像创建一台临时云服务器。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   创建云服务器时，只能选择通用计算型、2 vCPU、内存为4G及以上的KVM类型的规格。
    >-   通过ISO镜像创建云服务器必须创建两块盘，一块系统盘一块数据盘，在安装操作系统时，操作系统默认安装至数据盘中。

    1.  发送“POST https://\{ECS的Endpoint\}/v1/\{project\_id\}/cloudservers”。
    2.  在Request Header中增加“X-Auth-Token”。
    3.  在Request Body中传入如下参数：

        以下参数均为必填项，详细的参数说明请参见“[创建云服务器（按需）](https://support.huaweicloud.com/api-ecs/zh-cn_topic_0020212668.html#section2)”。

        ```
        {
            "server": {
                "imageRef": "fac42d61-ea1e-4271-94ba-6543a852d2c6",  //上一步获取的镜像ID
                "flavorRef": "rc6.large.2_manage",
                "name": "instance-test",
                "vpcid": "18ec99f0-7159-4d7b-ad27-f32315d5af61",
                "nics": [{
                    "subnet_id": "81a4ecb0-0451-4c60-8373-8b923238ec40"
                }],
                "root_volume": {
                    "volumetype": "SATA",
                    "size": "40"
                },
                "data_volumes": [{
                    "volumetype": "SATA",
                    "size": "40"
                }],
                "availability_zone": "az-1a",
                "metadata": {
                    "virtual_env_type": "IsoImage"
                },
                "extendparam": {
                    "diskPrior": "true"
                }
            }
        }
        ```

    4.  请求响应成功后，返回job\_id，根据job\_id查询job详情，可以获取云服务器ID。具体操作请参考“[查询任务的执行状态](https://support.huaweicloud.com/api-ecs/ecs_02_0901.html)”。
    5.  根据云服务器ID查询云服务器详情，可以获取[4](#zh-cn_topic_0219577800_li1053785582214)中需要用到的数据卷ID（volume\_id）。具体操作请参考“[查询云服务器详情](https://support.huaweicloud.com/api-ecs/ecs_02_0104.html)”。

4.  <a name="zh-cn_topic_0219577800_li1053785582214"></a>使用临时云服务器创建标准私有镜像。
    1.  发送“POST https://\{IMS的Endpoint\}/v2/cloudimages/action”。
    2.  在Request Header中增加“X-Auth-Token”。
    3.  在Request Body中传入如下参数：

        详细的参数说明请参见“[制作镜像](制作镜像.md)”。

        ```
        {
            "name": "ims_test",  //镜像名称（必填String）
            "description": "数据卷制作系统盘镜像",  //镜像描述（非必填String）
            "volume_id": "877a2cda-ba63-4e1e-b95f-e67e48b6129a",  //数据卷ID（必填String）
            "type": "ECS",  //镜像的类型（必填String）
            "os_version": "CentOS 7.0 64bit",  //操作系统版本（必填String）
            "image_tags": [{"key":"key2","value":"value2"},{"key":"key1","value":"value1"}]  //镜像标签列表（非必填Array of objects）
        }
        ```

    4.  请求响应成功后，返回job\_id，根据job\_id查询job详情，可以获取镜像ID。具体操作请参考[异步任务查询](异步任务查询.md)。


