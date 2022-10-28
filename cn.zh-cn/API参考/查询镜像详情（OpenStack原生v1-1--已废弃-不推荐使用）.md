# 查询镜像详情（OpenStack原生v1.1--已废弃，不推荐使用）<a name="ims_03_0710"></a>

## 功能介绍<a name="section21608354152128"></a>

查询镜像列表详情。

当前接口已废弃，推荐使用[查询镜像列表（OpenStack原生）](查询镜像列表（OpenStack原生）.md)。

## URI<a name="section49016415152128"></a>

GET /v1.1/images/detail

## 请求消息<a name="section49535636152128"></a>

-   请求参数

    可以把name、container\_format、disk\_format、status、size\_min、size\_max、changes-since作为uri参数，过滤查询结果。

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|name|否|String|镜像名称。name参数说明请参考镜像属性。|
|container_format|否|String|镜像容器类型|
|disk_format|否|String|镜像文件格式|
|status|否|String|镜像状态|
|size_min|否|String|镜像不小于|
|size_max|否|String|镜像不大于|
|changes-since|否|String|镜像最后更新时间|


-   请求样例

    ```
    GET https://{Endpoint}/v1.1/images/detail?disk_format=qcow2
    ```


## 响应消息<a name="section55994653152128"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|status|String|镜像状态|
|virtual_size|Integer|镜像虚拟大小|
|name|String|镜像名称。name参数说明请参考镜像属性。|
|deleted|Boolean|镜像是否已删除|
|container_format|String|镜像容器类型|
|created_at|String|镜像创建时间|
|disk_format|String|镜像文件类型|
|updated_at|String|镜像更新时间|
|properties|Object|镜像属性|
|owner|String|镜像所属租户|
|protected|Boolean|镜像是否受保护|
|min_ram|Integer|运行镜像所需最小内存，单位MB|
|checksum|String|镜像校验和，上传镜像文件后存在|
|min_disk|Integer|运行镜像所需最小磁盘，单位GB|
|is_public|Boolean|是否为公共镜像|
|deleted_at|String|镜像删除时间|
|id|String|镜像UUID|
|size|Integer|镜像大小，上传镜像文件后存在|


-   响应样例

    ```
    HTTP/1.1 200 OK
    ```

    ```
    Content-Type: application/json; charset=UTF-8
    Content-Length: 495
    X-Openstack-Request-Id: req-68327dda-8078-41fe-b091-01a09ec073da
    Date: Mon, 23 May 2016 02:32:28 GMT
    {
        "images": [
            {
                "status": "active",
                "deleted_at": null,
                "name": "cirros",
                "deleted": false,
                "container_format": "bare",
                "created_at": "2016-05-22T06:04:20.425843",
                "disk_format": "qcow2",
                "updated_at": "2016-05-22T06:04:22.719791",
                "min_disk": 0,
                "protected": false,
                "id": "3c3d1d01-b48a-4639-8a88-08be3b9b5d78",
                "min_ram": 0,
                "checksum": "64d7c1cd2b6f60c92c14662941cb7913",
                "owner": "23f4cb75768d4febb39542ef6fe169f3",
                "is_public": true,
                "virtual_size": null,
                "properties": {
                },
                "size": 13167616
            }
        ]
    }
    ```


## 返回值<a name="section61208656152128"></a>

-   正常

    200

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



