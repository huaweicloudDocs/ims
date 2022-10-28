# 查询镜像成员列表视图（OpenStack原生）<a name="ims_03_0718"></a>

## 功能介绍<a name="section16441043104828"></a>

该接口主要用于查询镜像成员列表视图，通过视图，用户可以了解到镜像成员包含哪些属性，同时也可以了解每个属性的数据类型。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceListImageMemberSchemas)中调试该接口。

## URI<a name="section40142579104828"></a>

GET /v2/schemas/members

## 请求消息<a name="section40279828104828"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/schemas/members
    ```


## 响应消息<a name="section1248471104828"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|name|String|视图名称。|
|links|Array of objects|视图链接。详情请参见表1。|
|properties|Object|镜像属性说明，主要是对基础属性的说明，包含每个属性的取值类型，用途。具体参数说明可参考镜像属性。|


    **表 1**  links字段说明

|参数|参数类型|描述|
|--|--|--|
|href|String|域名。|
|rel|String|域名描述。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {
        "name": "members",
        "links": [
            {
                "href": "{schema}",
                "rel": "describedby"
            }
        ],
        "properties": {
            "members": {
                "items": {
                    "name": "member",
                    "properties": {
                        "status": {
                            "enum": [
                                "pending",
                                "accepted",
                                "rejected"
                            ],
                            "type": "string",
                            "description": "The status of this image member"
                        },
                        "created_at": {
                            "type": "string",
                            "description": "Date and time of image member creation"
                        },
                        "updated_at": {
                            "type": "string",
                            "description": "Date and time of last modification of image member"
                        },
                        "image_id": {
                            "pattern": "^([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}$",
                            "type": "string",
                            "description": "An identifier for the image"
                        },
                        "member_id": {
                            "type": "string",
                            "description": "An identifier for the image member (tenantId)"
                        },
                        "schema": {
                            "readOnly": true,
                            "type": "string"
                        }
                    }
                },
                "type": "array"
            },
            "schema": {
                "type": "string"
            }
        }
    }
    ```


## 返回值<a name="section57883339104828"></a>

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



