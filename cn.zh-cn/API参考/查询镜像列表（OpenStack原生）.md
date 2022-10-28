# 查询镜像列表（OpenStack原生）<a name="ims_03_0702"></a>

## 功能介绍<a name="section59471393"></a>

获取镜像列表。

使用本接口查询镜像列表时，需要使用分页查询才能返回全部的镜像列表。

## 分页说明<a name="section165587269201"></a>

分页是指返回一组镜像的一个子集，在返回的时候会存在下个子集的链接和首个子集的链接，默认返回的子集中数量为25，用户也可以通过使用limit和marker两个参数自己分页，指定返回子集中需要返回的数量。

响应中的参数first是查询首页的URL。next是查询下一页的URL。当查询镜像列表最后一页时，不存在next。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceListImages)中调试该接口。

## URI<a name="section65480490"></a>

GET /v2/images

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   可以在URI后面用‘?’和‘&’添加不同的查询条件组合，请参考请求样例。
>-   如需使用OpenStack Queens版本API，请在请求消息头中包含X-Api-Version。当X-Api-Version取值大于M则返回Queens版本的结果，小于等于M，返回Mitaka版本结果 。

参数说明请参见[表1](#table33420935171457)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|__isregistered|否|String|镜像是否可用，取值为true，扩展接口会默认为true，普通用户只能查询取值为true的镜像。|
|__imagetype|否|String|镜像类型，目前支持以下类型：公共镜像：gold私有镜像：private共享镜像：shared市场镜像：market|
|protected|否|Boolean|镜像是否是受保护，取值为true/false。一般查询公共镜像时候取值为true，查询私有镜像可以不指定。|
|visibility|否|String|是否被其他租户可见，取值如下：public：公共镜像private：私有镜像shared：共享镜像|
|owner|否|String|镜像属于哪个租户。|
|id|否|String|镜像ID。|
|status|否|String|镜像状态。取值如下：queued：表示镜像元数据已经创建成功，等待上传镜像文件。saving：表示镜像正在上传文件到后端存储。deleted：表示镜像已经删除。killed：表示镜像上传错误。active：表示镜像可以正常使用。|
|name|否|String|镜像名称，匹配规则为精确匹配。name参数说明请参考镜像属性。|
|container_format|否|String|容器类型。默认值是bare。|
|disk_format|否|String|镜像格式，目前支持vhd、zvhd、raw、qcow2。默认值是vhd。|
|min_ram|否|Integer|镜像运行需要的最小内存，单位为MB。参数取值依据云服务器的规格限制，一般设置为0。云服务器的规格限制，请参见规格清单。|
|min_disk|否|Integer|镜像运行需要的最小磁盘，单位为GB 。取值为40～1024GB。|
|__os_bit|否|String|操作系统位数，一般取值为32或者64。|
|__platform|否|String|镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。|
|marker|否|String|用于分页，表示从哪个镜像开始查询，取值为镜像ID。|
|limit|否|Integer|用于分页，表示查询几条镜像记录，取值为整数，默认返回25条镜像记录。|
|sort_key|否|String|用于排序，表示按照哪个字段排序。取值为镜像属性name、container_format、disk_format、status、id、size、create_at字段，默认为创建时间。|
|sort_dir|否|String|用于排序，表示升序还是降序，取值为asc和desc。与sort_key一起组合使用，默认为降序desc。|
|__os_type|否|String|镜像系统类型，取值为Linux、Windows、Other。|
|tag|否|String|标签，用户为镜像增加自定义标签后可以通过该参数过滤查询。系统近期对标签功能进行了升级。如果之前添加的Tag为“Key.Value”的形式，则查询的时候需要使用“Key=Value”的格式来查询。例如：之前添加的tag为“a.b”,则升级后，查询时需使用“tag=a=b”。|
|member_status|否|String|成员状态。目前取值有accepted、rejected、pending。accepted表示已经接受共享的镜像，rejected表示已经拒绝了其他用户共享的镜像，pending表示需要确认的其他用户的共享镜像。需要在查询时，设置“visibility”参数为“shared”。|
|__support_kvm|否|String|如果镜像支持KVM，取值为true，否则无需增加该属性。|
|__support_xen|否|String|如果镜像支持XEN，取值为true，否则无需增加该属性。|
|__support_largememory|否|String|表示该镜像支持超大内存。如果镜像支持超大内存，取值为true，否则无需增加该属性。|
|__support_diskintensive|否|String|表示该镜像支持密集存储。如果镜像支持密集存储性能，则值为true，否则无需增加该属性。|
|__support_highperformance|否|String|表示该镜像支持高计算性能。如果镜像支持高计算性能，则值为true，否则无需增加该属性。|
|__support_xen_gpu_type|否|String|表示该镜像是支持XEN虚拟化平台下的GPU类型。支持GPU加速型实例的镜像操作系统类型请参考表2。如果不支持XEN虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_gpu_type|否|String|表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考表3。如果不支持KVM虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_xen_hana|否|String|如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_infiniband|否|String|如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无需添加该属性。该属性与“__support_xen”属性不共存。|
|created_at|否|String|镜像创建时间。支持按照时间点过滤查询，取值格式为“ 操作符:UTC时间”。其中操作符支持如下几种：gt：大于gte：大于等于lt：小于lte：小于等于eq：等于neq：不等于时间格式支持：yyyy-MM-ddThh:mm:ssZ或者yyyy-MM-dd hh:mm:ss例如，查询创建时间在2018-10-28 10:00:00之前的镜像，可以通过如下条件过滤：created_at=lt:2018-10-28T10:00:00Z|
|updated_at|否|String|镜像修改时间。支持按照时间点过滤查询，取值格式为 “ 操作符:UTC时间”。其中操作符支持如下几种：gt：大于gte：大于等于lt：小于lte：小于等于eq：等于neq：不等于时间格式支持：yyyy-MM-ddThh:mm:ssZ或者yyyy-MM-dd hh:mm:ss例如，查询修改时间在2018-10-28 10:00:00之前的镜像，可以通过如下条件过滤：updated_at=lt:2018-10-28T10:00:00Z|


## 常用列表查询方法<a name="section105891407155"></a>

-   公共镜像列表查询

    GET /v2/images?\_\_imagetype=gold&visibility=public&protected=true

-   私有镜像列表查询

    GET /v2/images?owner=\{project\_id\}

-   可以使用的共享镜像列表

    GET /v2/images?member\_status=accepted&visibility=shared&\_\_imagetype=shared

-   被拒绝的共享镜像列表

    GET /v2/images?member\_status=rejected&visibility=shared&\_\_imagetype=shared

-   未接受的共享镜像列表

    GET /v2/images?member\_status=pending&visibility=shared&\_\_imagetype=shared


## 请求消息<a name="section52453505"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images
    ```


## 响应消息<a name="section10077261173340"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|first|String|查询首页的URL。|
|next|String|查询下一页的URL。当查询镜像列表最后一页时，不存在next。|
|schema|String|描述镜像列表模式的URL。|
|images|Array of objects|资源类型。具体请参见表2。|


    **表 2**  images字段说明

|参数|参数类型|描述|
|--|--|--|
|__backup_id|String|备份ID。如果是备份创建的镜像，则填写为备份的ID，否则无此参数。|
|__data_origin|String|镜像来源。公共镜像为空。|
|__description|String|镜像描述信息。|
|__image_location|String|镜像的存储位置。|
|__image_size|String|镜像文件的大小，单位为字节。目前取值为大于0的字符串。|
|__image_source_type|String|镜像后端存储类型，目前只支持uds。|
|__is_config_init|String|是否完成了初始化配置。取值为“true”或“false”。|
|__isregistered|String|镜像是否可用，取值为true，扩展接口会默认为true，普通用户只能查询取值为true的镜像。|
|__lazyloading|String|镜像是否支持延迟加载。取值为true、false、True或False。|
|__originalimagename|String|父镜像ID。公共镜像或通过文件创建的私有镜像，取值为空。|
|__imagetype|String|镜像类型，目前支持以下类型：公共镜像：gold私有镜像：private共享镜像：shared市场镜像：market|
|protected|Boolean|镜像是否是受保护，查询公共镜像时候取值为true，查询私有镜像可以不指定。|
|virtual_env_type|String|镜像使用的环境类型：FusionCompute、Ironic、DataImage、IsoImage。如果是云服务器镜像（即系统盘镜像），则取值为FusionCompute。如果是数据卷镜像，则取值是DataImage。如果是裸金属服务器镜像，则取值是Ironic。如果是ISO镜像，则取值是IsoImage。|
|virtual_size|Integer|目前暂时不使用。|
|visibility|String|是否被其他租户可见。取值如下：public：表示公共镜像。private：表示私有镜像。shared：表示共享镜像。|
|owner|String|镜像属于哪个租户。|
|id|String|镜像ID。|
|status|String|镜像状态。取值如下：queued：表示镜像元数据已经创建成功，等待上传镜像文件。saving：表示镜像正在上传文件到后端存储。deleted：表示镜像已经删除。killed：表示镜像上传错误。active：表示镜像可以正常使用。|
|name|String|镜像名称。name参数说明请参考镜像属性。|
|container_format|String|容器类型。|
|disk_format|String|镜像格式，目前支持vhd、zvhd、raw、qcow2。默认值是vhd。|
|min_ram|Integer|镜像运行需要的最小内存，单位为MB。参数取值依据云服务器的规格限制，一般为0。云服务器的规格限制，请参见规格清单。|
|max_ram|String|镜像支持的最大内存，单位为MB。|
|min_disk|Integer|镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。|
|__os_bit|String|操作系统位数，一般取值为32或者64。|
|__os_feature_list|String|镜像附加属性。该属性采用JSON格式来标识镜像支持的高级特性清单。|
|__platform|String|镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。|
|schema|String|镜像视图。|
|self|String|镜像链接信息。|
|size|Integer|目前暂时不使用。|
|__os_type|String|镜像系统类型，取值为Linux、Windows、Other。|
|__os_version|String|操作系统具体版本。|
|tags|Array of strings|镜像标签列表，提供用户可以自定义管理私有镜像的能力。|
|__support_kvm|String|如果镜像支持KVM，取值为true，否则无此属性。|
|__support_xen|String|如果镜像支持XEN，取值为true，否则无此属性。|
|__support_largememory|String|表示该镜像支持超大内存。如果镜像支持超大内存，取值为true，否则无此属性。|
|__support_diskintensive|String|表示该镜像支持密集存储。如果镜像支持密集存储性能，则值为true，否则无此属性。|
|__support_highperformance|String|表示该镜像支持高计算性能。如果镜像支持高计算性能，则值为true，否则无此属性。|
|__support_xen_gpu_type|String|表示该镜像是支持XEN虚拟化平台下的GPU类型。支持GPU加速型实例的镜像操作系统类型请参考表2。如果不支持XEN虚拟化下GPU类型，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_gpu_type|String|表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考表3。如果不支持KVM虚拟化下GPU类型，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_xen_hana|String|如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。|
|__support_kvm_infiniband|String|如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无此属性。该属性与“__support_xen”属性不共存。|
|__productcode|String|市场镜像的产品ID。|
|__root_origin|String|表示当前镜像来源是从外部导入。取值样例：file。|
|__sequence_num|String|表示当前镜像对应云服务器的系统盘插槽位置。取值样例：0。|
|__support_fc_inject|String|表示当前镜像支持Cloud-Init密码/密钥注入方式。如果取值为“true”，表示该镜像不支持Cloud-Init注入密码/密钥，其他取值时表示支持Cloud-Init注入密钥/密码。该特性参数只对ECS系统盘镜像生效，其他类型镜像不生效。|
|__is_offshelved|String|表示当前市场镜像是否下架。true：已下架false：未下架|
|created_at|String|创建时间。格式为UTC时间。|
|updated_at|String|更新时间。格式为UTC时间。|
|active_at|String|镜像状态变为正常的时间。|
|checksum|String|目前暂时不使用。|
|hw_firmware_type|String|云服务器的启动方式。目前支持：bios：表示bios引导启动。uefi：表示uefi引导启动。|
|file|String|镜像文件下载和上传链接。|
|enterprise_project_id|String|表示当前镜像所属的企业项目。取值为0或无该值，表示属于default企业项目。取值为UUID，表示属于该UUID对应的企业项目。|
|__support_arm|String|是否是ARM架构类型的镜像。取值为“true”或者“false”。|
|__support_agent_list|String|镜像是否支持企业主机安全或主机监控。hss：企业主机安全ces：主机监控取值样例："__support_agent_list": "hss,ces"如果查询结果无此字段，表示镜像不支持企业主机安全或主机监控。|
|__account_code|string|收费镜像标识。|
|__support_amd|String|是否是AMD架构类型的镜像。取值为“true”或者“false”。|
|__system__cmkid|String|加密镜像所使用的密钥ID。|
|hw_vif_multiqueue_enabled|String|镜像是否支持网卡多队列。取值为“true”或者“false”。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {
      "schema": "/v2/schemas/images",
      "next": "/v2/images?__isregistered=true&marker=0328c25e-c840-4496-81ac-c4e01b214b1f&__imagetype=gold&limit=2",
      "images": [
        {
          "schema": "/v2/schemas/image",
          "min_disk": 100,
          "created_at": "2018-09-06T14:03:27Z",
          "__image_source_type": "uds",
          "container_format": "bare",
          "file": "/v2/images/bc6bed6e-ba3a-4447-afcc-449174a3eb52/file",
          "updated_at": "2018-09-06T15:17:33Z",
          "protected": true,
          "checksum": "d41d8cd98f00b204e9800998ecf8427e",
          "id": "bc6bed6e-ba3a-4447-afcc-449174a3eb52",
          "__isregistered": "true",
          "min_ram": 2048,
          "__lazyloading": "true",
          "owner": "1bed856811654c1cb661a6ca845ebc77",
          "__os_type": "Linux",
          "__imagetype": "gold",
          "visibility": "public",
          "virtual_env_type": "FusionCompute",
          "tags": [],
          "__platform": "CentOS",
          "size": 0,
          "__os_bit": "64",
          "__os_version": "CentOS 7.3 64bit",
          "name": "CentOS 7.3 64bit vivado",
          "self": "/v2/images/bc6bed6e-ba3a-4447-afcc-449174a3eb52",
          "disk_format": "zvhd2",
          "virtual_size": null,
          "hw_firmware_type": "bios",
          "status": "active"
        },
        {
          "schema": "/v2/schemas/image",
          "min_disk": 100,
          "created_at": "2018-09-06T14:03:05Z",
          "__image_source_type": "uds",
          "container_format": "bare",
          "file": "/v2/images/0328c25e-c840-4496-81ac-c4e01b214b1f/file",
          "updated_at": "2018-09-25T14:27:40Z",
          "protected": true,
          "checksum": "d41d8cd98f00b204e9800998ecf8427e",
          "id": "0328c25e-c840-4496-81ac-c4e01b214b1f",
          "__isregistered": "true",
          "min_ram": 2048,
          "__lazyloading": "true",
          "owner": "1bed856811654c1cb661a6ca845ebc77",
          "__os_type": "Linux",
          "__imagetype": "gold",
          "visibility": "public",
          "virtual_env_type": "FusionCompute",
          "tags": [],
          "__platform": "CentOS",
          "size": 0,
          "__os_bit": "64",
          "__os_version": "CentOS 7.3 64bit",
          "name": "CentOS 7.3 64bit with sdx",
          "self": "/v2/images/0328c25e-c840-4496-81ac-c4e01b214b1f",
          "disk_format": "zvhd2",
          "virtual_size": null,
          "hw_firmware_type": "bios",
          "status": "active"
        }
      ],
      "first": "/v2/images?__isregistered=true&__imagetype=gold&limit=2"
    }
    ```


## 返回值<a name="section20875522"></a>

-   正常

    200

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误，具体返回错误码请参考错误码。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



