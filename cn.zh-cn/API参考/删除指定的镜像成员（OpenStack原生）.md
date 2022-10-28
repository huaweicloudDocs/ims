# 删除指定的镜像成员（OpenStack原生）<a name="ims_03_0724"></a>

## 功能介绍<a name="section29995926"></a>

该接口用于取消对某个用户的镜像共享。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteImageMember)中调试该接口。

## URI<a name="section1527883"></a>

DELETE /v2/images/\{image\_id\}/members/\{member\_id\}

参数说明请参见[表1](#table6209770492526)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|
|member_id|是|String|成员ID|


## 请求消息<a name="section13750947"></a>

-   请求参数

    无

-   请求样例

    ```
    DELETE https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
    ```


## 响应消息<a name="section56649665"></a>

-   响应参数

    无

-   响应样例

    ```
    204 No Content
    ```


## 返回值<a name="section61705107"></a>

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



