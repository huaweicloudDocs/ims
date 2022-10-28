# 更新镜像成员状态（OpenStack原生）<a name="ims_03_0721"></a>

## 功能介绍<a name="section39958021"></a>

用户接受或者拒绝共享镜像时，使用该接口更新镜像成员的状态。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceUpdateImageMember)中调试该接口。

## URI<a name="section24077873"></a>

PUT /v2/images/\{image\_id\}/members/\{member\_id\}

参数说明请参见[表1](#table37590215162351)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|
|member_id|是|String|成员ID|


## 请求消息<a name="section15374270"></a>

-   请求参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|status|是|String|镜像成员的状态。取值如下：accepted：表示接受共享镜像。接受后，该镜像在用户镜像列表中可见，用户可以使用该镜像创建云服务器。rejected：表示拒绝共享镜像。拒绝后，该镜像在用户镜像列表中不可见，但是，用户仍然可以使用该镜像创建云服务器。|
|vault_id|否|String|存储库ID。如果是CBR创建的整机镜像，则在接受该共享镜像时，为必选参数，需传入该值。存储库ID可以从云备份服务控制台获取，或者参考“查询存储库列表”查询。|


-   请求样例
    -   镜像为非整机镜像时

        ```
        PUT https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
        ```

        ```
        {
            "status": "accepted"
        }
        ```

    -   镜像为整机镜像时

        ```
        PUT https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
        ```

        ```
        {
            "status": "accepted",
            "vault_id": "6yhtb5df-1bc3-4c3f-893e-3e4716yhgt61"
        }
        ```



## 响应消息<a name="section4150710"></a>

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



