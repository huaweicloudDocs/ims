# 更新镜像信息（OpenStack原生）<a name="ims_03_0704"></a>

## 功能介绍<a name="section16095919"></a>

修改镜像信息。

## 约束与限制<a name="section4659381317371"></a>

更新镜像目前只能更新用户自定义属性，或者镜像的名称和描述信息，其他属性不允许用户更新。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceUpdateImage)中调试该接口。

## URI<a name="section10645546"></a>

PATCH /v2/images/\{image\_id\}

参数说明请参见[表1](#table30282311)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID。如何获取镜像ID，请参见查询镜像列表。|


## 请求消息<a name="section28701056"></a>

-   请求参数

    Glance有两种方式的更新操作，通过http header里的Content-Type指定，当前支持“application/openstack-images-v2.0-json-patch”、“application/openstack-images-v2.1-json-patch”两种Content-Type。不同的Content-Type区别只是请求消息体格式不同。

    **表 2**  v2.1版本请求消息体

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|*[数组]*|是|Array of objects|详情请参见表3。|


    **表 3** _\[数组\]_字段说明

|参数|参数类型|是否必选|描述|
|--|--|--|--|
|op|String|是|所需进行的更新操作的类型：替换、添加、删除。取值范围：replace、add、remove|
|path|String|是|所要操作的属性名称。replace和remove操作取值只能是镜像当前已有的属性；add操作取值可以为当前已有属性和不存在的属性，如果为已有属性则执行效果同replace，如果是不存在的属性则执行add，需要在属性名称前加“/”。|
|value|String|否|所需更新/添加属性的值。根据op的value决定，replace、add需要指定，remove不需要|


    **表 4**  v2.0版本请求消息体

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|*[数组]*|是|Array of objects|详情请参见表5。|


    **表 5** _\[数组\]_字段说明

|参数|参数类型|是否必选|描述|
|--|--|--|--|
|replace|String|取值三选一|key为replace表示替换镜像的相关属性，值为所要替换的属性需要在属性名称前加“/”|
|add|String|key为add表示添加镜像属性，值为所要添加的属性名称，需要在属性名称前加“/”|
|remove|String|key为remove表示删除镜像属性，值为所要删除的属性名称需要在属性名称前加“/”|
|value|String|根据前面的key决定，replace和add需要指定，remove不需要。|所需更新/添加的属性的值。参数说明请参考镜像属性。|


-   请求样例

    ```
    PATCH https://{Endpoint}/v2/images/33ad552d-1149-471c-8190-ff6776174a00
    ```

    -   V2.1版本请求体

        ```
        "Content-Type:application/openstack-images-v2.1-json-patch"   
        [
             {
                 "op": "replace",
                 "path": "/name",
                 "value": "test01"
             }
        ]
        ```

    -   V2.0版本请求体

        ```
        "Content-Type:application/openstack-images-v2.0-json-patch"
        [
             {
                 "replace": "/name",
                 "value": "test01"       
             }
        ]     
        ```



## 响应消息<a name="section56982912"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|file|String|镜像文件下载和上传链接。|
|owner|String|镜像属于哪个租户。|
|id|String|镜像ID。|
|size|Long|目前暂时不使用。|
|self|String|镜像链接信息。|
|schema|String|镜像视图。|
|status|String|镜像状态。取值如下：queued：表示镜像元数据已经创建成功，等待上传镜像文件。saving：表示镜像正在上传文件到后端存储。deleted：表示镜像已经删除。killed：表示镜像上传错误。active：表示镜像可以正常使用。|
|tags|Array of strings|镜像标签列表，提供用户可以自定义管理私有镜像的能力。用户可以通过镜像标签接口为每个镜像增加不同的标签，在查询接口中可以根据标签进行过滤。|
|visibility|String|是否被其他租户可见。取值如下：private：私有镜像public：公共镜像shared：共享镜像|
|name|String|镜像名称。name参数说明请参考镜像属性。|
|checksum|String|目前暂时不使用。|
|protected|Boolean|是否是受保护的，受保护的镜像不允许删除。取值为true或false。|
|container_format|String|容器类型。|
|min_ram|Integer|镜像运行需要的最小内存，单位为MB。参数取值依据云服务器的规格限制，默认设置为0。云服务器的规格限制，请参见规格清单。|
|max_ram|String|镜像支持的最大内存，单位为MB。参数取值可以参考云服务器的规格限制，默认不设置。云服务器的规格限制，请参见规格清单。|
|updated_at|String|更新时间。格式为UTC时间。|
|__os_bit|String|操作系统位数，一般取值为“32”或者“64”。|
|__os_version|String|操作系统具体版本。|
|__description|String|镜像描述信息。_description参数说明请参考镜像属性。|
|disk_format|String|镜像的格式，目前支持vhd、zvhd、zvhd2、raw、qcow2、iso。默认值是vhd。|
|__isregistered|String|是否是注册过的镜像，取值为“true”或者“false”。|
|__platform|String|镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。|
|__os_type|String|操作系统类型，目前取值Linux、Windows、Other。|
|__system__cmkid|String|加密镜像所使用的密钥ID。|
|min_disk|Integer|镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。|
|virtual_env_type|String|镜像使用环境类型：FusionCompute、Ironic、DataImage、IsoImage。如果是云服务器镜像（即系统盘镜像），则取值为FusionCompute。如果是数据卷镜像，则取值是DataImage。如果是裸金属服务器镜像，则取值是Ironic。如果是ISO镜像，则取值是IsoImage。|
|__image_source_type|String|镜像后端存储类型，目前只支持uds。|
|__imagetype|String|镜像类型，目前支持：公共镜像（gold）私有镜像（private）共享镜像（shared）市场镜像（market）|
|created_at|String|创建时间。格式为UTC时间。|
|virtual_size|Integer|目前暂时不使用。|
|__originalimagename|String|父镜像ID。公共镜像或通过文件创建的私有镜像，取值为空。|
|__backup_id|String|备份ID。如果是备份创建的镜像，则填写为备份的ID，否则无此参数。|
|__productcode|String|市场镜像的产品ID。|
|__image_size|String|镜像文件的大小，单位为字节。必须大于0。|
|__data_origin|String|镜像来源。公共镜像为空。|
|__root_origin|String|表示当前镜像来源是从外部导入。取值：file。|
|__lazyloading|String|镜像是否支持延迟加载。取值为true、false、True或False。|
|active_at|String|镜像状态变为正常的时间。|
|__os_feature_list|String|镜像附加属性。该属性采用JSON格式来标识镜像支持的高级特性清单。|
|__account_code|String|收费镜像标识。|
|hw_firmware_type|String|云服务器的启动方式。目前支持：bios：表示bios引导启动。如果无此参数，表示bios启动方式。uefi：表示uefi引导启动。当镜像的架构类型为ARM时，启动方式只支持uefi。|
|hw_vif_multiqueue_enabled|String|镜像是否支持网卡多队列。取值为“true”或者“false”。|
|__support_kvm|String|如果镜像支持KVM，取值为true，否则无需增加该属性。|
|__support_xen|String|如果镜像支持XEN，取值为true，否则无需增加该属性。|
|__support_largememory|String|表示该镜像是否支持超大内存特性。如果镜像支持超大内存，取值为true，否则无此属性。镜像操作系统类型请参考“弹性云服务器类型与支持的操作系统版本”。|
|__support_diskintensive|String|表示该镜像是否支持密集存储性特性。如果镜像支持密集存储性能，则值为true，否则无此属性。|
|__support_highperformance|String|表示该镜像是否支持高计算性能的特性。如果镜像支持高计算性能，则值为true，否则无此属性。|
|__support_xen_gpu_type|String|表示该镜像是支持XEN虚拟化平台下的GPU类型，取值参考表2。如果不支持，则无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_gpu_type|String|表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考表3。如果不支持，则无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_xen_hana|String|如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_infiniband|String|如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无此属性。该属性与“__support_xen”属性不共存。|
|__is_offshelved|String|表示当前市场镜像是否下架。true：已下架false：未下架|
|enterprise_project_id|String|表示当前镜像所属的企业项目。取值为0或无该值，表示属于default企业项目。取值为UUID，表示属于该UUID对应的企业项目。关于企业项目特性的详细信息，请参考“企业中心总览”。|
|__sequence_num|String|表示当前镜像对应云服务器的系统盘插槽位置。目前暂不使用。|
|__support_fc_inject|String|表示当前镜像支持Cloud-Init密码/密钥注入方式。如果取值为“true”，表示该镜像不支持Cloud-Init注入密码/密钥，其他取值时表示支持Cloud-Init注入密钥/密码。该特性参数只对ECS系统盘镜像生效，其他类型镜像不生效。|
|__support_arm|String|是否为ARM架构类型的镜像。取值为“true”或者“false”。|
|__image_location|String|镜像的存储位置。|
|__is_config_init|String|是否完成了初始化配置。取值为“true”或者“false”。|
|__support_amd|String|是否是AMD架构类型的镜像。取值为“true”或者“false”。|
|__support_agent_list|String|镜像是否支持企业主机安全或主机监控。hss：企业主机安全ces：主机监控取值样例："__support_agent_list": "hss,ces"如果查询结果无此字段，表示镜像不支持企业主机安全或主机监控。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {  
        "file": "/v2/images/33ad552d-1149-471c-8190-ff6776174a00/file",  
        "owner": "0b1e494e2660441a957313163095fe5c",  
        "id": "33ad552d-1149-471c-8190-ff6776174a00",  
        "size": 2,  
        "self": "/v2/images/33ad552d-1149-471c-8190-ff6776174a00",  
        "schema": "/v2/schemas/image",  
        "status": "active",  
        "tags": [],  
        "visibility": "private",  
        "name": "ims_test",  
        "checksum": "99914b932bd37a50b983c5e7c90ae93b",  
        "protected": false,  
        "container_format": "bare",  
        "min_ram": 0,  
        "updated_at": "2015-12-08T02:30:49Z",  
        "__os_bit": "64",  
        "__os_version": "Ubuntu 14.04 server 64bit",  
        "__description": "ims test",  
        "disk_format": "vhd",  
        "__isregistered": "true",  
        "__platform": "Ubuntu",  
        "__os_type": "Linux",  
        "min_disk": 40,  
        "virtual_env_type": "FusionCompute",  
        "__image_source_type": "uds",  
        "__imagetype": "private",  
        "created_at": "2015-12-04T09:45:33Z",  
        "virtual_size": 0,  
        "__originalimagename": "33ad552d-1149-471c-8190-ff6776174a00",  
        "__backup_id": "",  
        "__productcode": "",  
        "__image_size": "449261568",  
        "__data_origin": null,
        "hw_firmware_type":"bios"
    }
    ```


## 返回值<a name="section43084165"></a>

-   正常

    200

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误，具体返回错误码请参错误码。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



