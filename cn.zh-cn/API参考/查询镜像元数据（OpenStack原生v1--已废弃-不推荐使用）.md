# 查询镜像元数据（OpenStack原生v1--已废弃，不推荐使用）<a name="ims_03_0709"></a>

## 功能介绍<a name="section6658307515228"></a>

查询镜像元数据。

当前接口已废弃，推荐使用[查询镜像详情（OpenStack原生）](查询镜像详情（OpenStack原生）.md)。

## URI<a name="section1935356215228"></a>

HEAD /v1/images/\{image\_id\}

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|


## 请求消息<a name="section6467246815228"></a>

-   请求参数

    无

-   请求样例

    ```
    HEAD https://{Endpoint}/v1/images/3c3d1d01-b48a-4639-8a88-08be3b9b5d78
    ```


## 响应消息<a name="section1674295515228"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|Status|String|镜像状态|
|Virtual_size|Integer|镜像虚拟大小|
|Name|String|镜像名称|
|Deleted|Boolean|镜像是否已删除|
|Container_format|String|镜像容器类型|
|Created_at|String|镜像创建时间|
|Disk_format|String|镜像文件类型|
|Updated_at|String|镜像更新时间|
|Property|Object|镜像属性|
|Owner|String|镜像所属租户|
|Protected|Boolean|镜像是否受保护|
|Min_ram|Integer|运行镜像所需最小内存，单位MB|
|Checksum|String|镜像校验和，上传镜像文件后存在|
|Min_disk|Integer|运行镜像所需最小磁盘，单位GB|
|Is_public|Boolean|是否为公共镜像|
|Deleted_at|String|镜像删除时间|
|Id|String|镜像UUID|
|Size|Integer|镜像大小，上传镜像文件后存在|


    上述响应参数在HTTP响应消息的header中返回。

-   响应样例

    ```
    HTTP/1.1 200 OK
    ```

    ```
    Content-Type: text/html; charset=UTF-8
    Content-Length: 0
    X-Image-Meta-Id: 3c3d1d01-b48a-4639-8a88-08be3b9b5d78
    X-Image-Meta-Deleted: False
    X-Image-Meta-Container_format: bare
    X-Image-Meta-Checksum: 64d7c1cd2b6f60c92c14662941cb7913
    X-Image-Meta-Protected: False
    X-Image-Meta-Min_disk: 0
    X-Image-Meta-Created_at: 2016-05-22T06:04:20.425843
    X-Image-Meta-Size: 13167616
    X-Image-Meta-Status: active
    X-Image-Meta-Is_public: True
    X-Image-Meta-Min_ram: 0
    X-Image-Meta-Owner: 23f4cb75768d4febb39542ef6fe169f3
    X-Image-Meta-Updated_at: 2016-05-22T06:04:22.719791
    X-Image-Meta-Disk_format: qcow2
    X-Image-Meta-Name: cirros
    Etag: 64d7c1cd2b6f60c92c14662941cb7913
    X-Openstack-Request-Id: req-7123ca83-da23-4f4e-9ed6-accd3707d333
    Date: Mon, 23 May 2016 02:29:54 GMT
    ```


## 返回值<a name="section6571722315228"></a>

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



