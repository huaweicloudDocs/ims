# 删除镜像（OpenStack原生）<a name="ims_03_0706"></a>

## 功能介绍<a name="section24723024"></a>

该接口主要用于删除镜像，用户可以通过该接口将自己的私有镜像删除。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteImage)中调试该接口。

## URI<a name="section21180630"></a>

DELETE /v2/images/\{image\_id\}

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|


## 请求消息<a name="section56407950"></a>

-   请求参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|delete_backup|否|Boolean|取值为：true和falsetrue：表示删除整机镜像时，同时删除其关联的云服务器备份或云备份。false：表示只删除整机镜像，不删除其关联的云服务器备份或云备份。|


-   请求样例

    ```
    DELETE https://{Endpoint}/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba90
    ```

    ```
    {
        "delete_backup": true
    }
    ```


## 响应消息<a name="section37909503"></a>

-   响应参数

    无

-   响应样例

    ```
    STATUS CODE 204
    ```


## 返回值<a name="section5641212"></a>

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



