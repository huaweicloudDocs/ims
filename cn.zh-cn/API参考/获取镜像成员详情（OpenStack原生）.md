# 获取镜像成员详情（OpenStack原生）<a name="ims_03_0722"></a>

## 功能介绍<a name="section16095919"></a>

该接口主要用于镜像共享中查询某个镜像成员的详情。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceShowImageMember)中调试该接口。

## URI<a name="section10645546"></a>

GET /v2/images/\{image\_id\}/members/\{member\_id\}

参数说明请参见[表1](#table30282311)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|
|member_id|是|String|成员ID|


## 请求消息<a name="section28701056"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
    ```


## 响应消息<a name="section56982912"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|status|String|共享状态|
|created_at|String|共享时间，格式为UTC时间|
|updated_at|String|更新时间，格式为UTC时间|
|image_id|String|镜像ID|
|member_id|String|成员ID|
|schema|String|共享视图|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {
        "status": "accepted",
        "created_at": "2016-09-01T02:05:14Z",
        "updated_at": "2016-09-01T02:37:11Z",
        "image_id": "d164b5df-1bc3-4c3f-893e-3e471fd16e64",
        "member_id": "edc89b490d7d4392898e19b2deb34797",
        "schema": "/v2/schemas/member"
    }
    ```


## 返回值<a name="section61374531"></a>

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



