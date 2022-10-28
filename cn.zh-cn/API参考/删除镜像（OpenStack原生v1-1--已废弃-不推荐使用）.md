# 删除镜像（OpenStack原生v1.1--已废弃，不推荐使用）<a name="ims_03_0708"></a>

## 功能介绍<a name="section65883044152228"></a>

删除镜像，软删除指定ID的镜像，镜像在库中依然保存，只将该镜像的status状态置为deleted。

当前接口已废弃，推荐使用[删除镜像（OpenStack原生）](删除镜像（OpenStack原生）.md)。

## URI<a name="section45901761152228"></a>

DELETE /v1.1/images/\{image\_id\}

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|


## 请求消息<a name="section59210700152228"></a>

-   请求参数

    无

-   请求样例

    ```
    DELETE https://{Endpoint}/v1.1/images/3c3d1d01-b48a-4639-8a88-08be3b9b5d78
    ```


## 响应消息<a name="section13601000152228"></a>

-   响应参数

    无

-   响应样例

    ```
    HTTP/1.1 200 OK
    ```

    ```
    Content-Type: text/html; charset=UTF-8
    Content-Length: 0
    X-Openstack-Request-Id: req-75e9edca-7b43-47da-bdc5-d39be469b72f
    Date: Mon, 23 May 2016 02:43:34 GMT
    ```


## 返回值<a name="section47464039152228"></a>

-   正常

    204

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



