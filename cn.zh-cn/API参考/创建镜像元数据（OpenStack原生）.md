# 创建镜像元数据（OpenStack原生）<a name="ims_03_0707"></a>

## 功能介绍<a name="section66302617144828"></a>

创建镜像元数据。

调用创建镜像元数据接口成功后，只是创建了镜像的元数据，镜像对应的实际镜像文件并不存在。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceCreateImageMetadata)中调试该接口。

## URI<a name="section16226363144828"></a>

POST /v2/images

## 请求消息<a name="section22707920144828"></a>

-   请求参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|__os_version|否|String|镜像的操作系统具体版本，取值范围见相关参数取值列表。如果未指定__os_version，则默认设置为Other Linux (64 bit)，不保证该镜像能成功创建虚拟机以及通过该镜像创建的虚拟机能够正常使用。|
|visibility|否|String|其他租户是否可见。默认取值为private。创建镜像元数据时，visibility取值只能为private。|
|name|否|String|镜像名称，如果未指定name的取值，则默认为空，但是使用该镜像创建虚拟机会失败。名称的长度为1～255位。name参数说明请参考镜像属性。默认值为空。|
|protected|否|Boolean|镜像是否被保护，保护后的镜像不可删除。默认取值为false。|
|container_format|否|String|容器格式。默认取值为bare。|
|disk_format|否|String|镜像文件格式。目前支持vhd、zvhd、zvhd2、raw、qcow2。默认取值为vhd。|
|tags|否|Array of strings|镜像标签列表。长度为1～255位。默认为空。|
|min_ram|否|Integer|镜像运行需要的最小内存，单位为MB。参数取值依据云服务器的规格限制。默认取值为0。云服务器的规格限制，请参见规格清单。|
|min_disk|否|Integer|镜像运行需要的最小磁盘，单位为GB 。取值为40～1024GB。必须大于镜像系统盘容量，否则创建云服务器可能失败。|


    >![](public_sys-resources/icon-note.gif) **说明：** 
    >可以在请求样例的body体中自定义key:value的字段，key字符串长度不超过255，value可以为空字符串。例如：
    >```
    >"key": "value"
    >```

-   请求样例

    ```
    POST https://{Endpoint}/v2/images
    ```

    ```
    {
        "__os_version": "Ubuntu 14.04 server 64bit",
        "container_format": "bare",
        "disk_format": "vhd",
        "min_disk": 1,
        "min_ram": 1024,
        "name": "test",
        "tags": [
            "test",
            "image"
        ],
        "visibility": "private",
        "protected": false
    }
    ```


## 响应消息<a name="section37386190144828"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|visibility|String|其他租户是否可见。取值为private。|
|name|String|镜像名称，如果未指定name的取值，则默认为空，但是使用该镜像创建虚拟机会失败。名称的长度为1～128位。name参数说明请参考镜像属性。|
|protected|Boolean|镜像是否被保护，保护后的镜像不可删除。取值为false。|
|container_format|String|容器格式。取值为bare。|
|disk_format|String|镜像文件格式。目前支持vhd、zvhd、raw、qcow2。默认值是vhd。|
|tags|Array of strings|镜像标签列表。长度为1～255位。|
|min_ram|Integer|镜像运行最小内存，单位为MB。取值参考ECS规格限制，一般设置为0。云服务器的规格限制，请参见规格清单。|
|min_disk|Integer|镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。必须大于镜像系统盘容量，否则创建云服务器可能失败。|
|status|String|镜像状态。取值如下：queued：表示镜像元数据已经创建成功，等待上传镜像文件。saving：表示镜像正在上传文件到后端存储。deleted：表示镜像已经删除。killed：表示镜像上传错误。active：表示镜像可以正常使用。|
|created_at|String|创建时间。格式为UTC时间。|
|updated_at|String|更新时间。格式为UTC时间。|
|self|String|本镜像链接。|
|id|String|镜像ID。用户调用创建镜像接口后，需保存该镜像的ID，用来调用上传镜像接口完成镜像上传。|
|file|String|上传下载镜像文件的地址链接。|
|schema|String|视图链接。|
|__image_source_type|String|镜像后端存储类型，目前支持uds。|
|__image_size|String|镜像大小。单位为字节。|
|__isregistered|String|镜像是否注册。只有已注册的镜像才能在Portal界面上查询到。取值为true。|
|__os_version|String|镜像的操作系统具体版本，取值范围见相关参数取值列表。|
|__os_type|String|镜像的操作系统类型，取值由__os_version确定。支持Windows、Linux和other。|
|__platform|String|表示镜像支持的操作系统平台。取值由__os_version确定。|
|__os_bit|String|表示操作系统位数。取值由__os_version确定，取值为32或64。|
|__imagetype|String|镜像类型。取值为private，表示私有镜像。|
|virtual_env_type|String|平台类型。镜像使用环境类型：FusionCompute、Ironic、DataImage、IsoImage。如果是云服务器镜像，则取值为FusionCompute。如果是数据卷镜像，则取值为DataImage。如果是裸金属服务器镜像，则取值为Ironic。如果是ISO镜像，则取值是IsoImage。|
|owner|String|镜像所属项目ID。|
|__root_origin|String|表示当前镜像来源是从外部导入。取值：file。|
|checksum|String|镜像文件md5值。|
|size|Long|目前暂时不使用。|
|virtual_size|Integer|镜像虚拟大小。单位为字节。|
|properties|Properties object|镜像属性的集合，不表示具体的镜像属性。|


-   响应样例

    ```
    STATUS CODE 201
    ```

    ```
    {
        "schema": "/v2/schemas/image",
        "min_disk": 1,
        "created_at": "2016-06-02T07:49:48Z",
        "__image_source_type": "uds",
        "container_format": "bare",
        "__image_size": "0",
        "file": "/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86/file",
        "updated_at": "2016-06-02T07:49:49Z",
        "protected": false,
        "id": "4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86",
        "__isregistered": "true",
        "min_ram": 1024,
        "owner": "b912fb4a4c464b568ecfca1071b21b10",
        "__os_type": "Linux",
        "__imagetype": "private",
        "visibility": "private",
        "virtual_env_type": "FusionCompute",
        "tags": [
            "test",
            "image"
        ],
        "__platform": "Ubuntu",
        "__os_bit": "64",
        "__os_version": "Ubuntu 14.04 server 64bit",
        "name": "test",
        "self": "/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86",
        "disk_format": "vhd",
        "status": "queued"
    }
    ```


## 返回值<a name="section55843593"></a>

-   正常

    201

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



