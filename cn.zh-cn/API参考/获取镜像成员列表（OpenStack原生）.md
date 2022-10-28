# 获取镜像成员列表（OpenStack原生）<a name="ims_03_0723"></a>

## 功能介绍<a name="section24723024"></a>

该接口用于共享镜像过程中，获取接受该镜像的成员列表。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceListImageMembers)中调试该接口。

## URI<a name="section21180630"></a>

GET /v2/images/\{image\_id\}/members

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|


## 请求消息<a name="section56407950"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members
    ```


## 响应消息<a name="section37909503"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|members|Array of objects|共享成员列表。详情请参见表2。|
|schema|String|共享视图。|


    **表 2**  members字段说明

|参数|参数类型|描述|
|--|--|--|
|status|String|共享状态。|
|created_at|String|共享时间，格式为UTC时间。|
|updated_at|String|更新时间，格式为UTC时间。|
|image_id|String|镜像ID。|
|member_id|String|成员ID。|
|schema|String|共享视图。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {
        "members": [
            {
                "status": "accepted",
                "created_at": "2016-09-01T02:05:14Z",
                "updated_at": "2016-09-01T02:37:11Z",
                "image_id": "d164b5df-1bc3-4c3f-893e-3e471fd16e64",
                "member_id": "edc89b490d7d4392898e19b2deb34797",
                "schema": "/v2/schemas/member"
            }
        ],
        "schema": "/v2/schemas/members"
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



