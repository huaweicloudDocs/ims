# 删除标签（OpenStack原生）<a name="ims_03_0713"></a>

## 功能介绍<a name="section18389930"></a>

该接口主要用于删除某个镜像的自定义标签，通过该接口，用户可以将私有镜像中一些不用的标签删除。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteTag)中调试该接口。

## URI<a name="section31291646"></a>

DELETE /v2/images/\{image\_id\}/tags/\{tag\}

参数说明请参见[表1](#table25869170205722)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID|
|tag|是|String|镜像的tag。字符串中不能包含“=”。|


## 请求消息<a name="section13189358"></a>

-   请求参数

    无

-   请求样例

    ```
    DELETE https://{Endpoint}/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba90/tags/aaaa
    ```


## 响应消息<a name="section51595365"></a>

-   响应参数

    无

-   响应样例

    ```
    STATUS CODE 204
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



