# 跨Region复制镜像<a name="ims_03_0628"></a>

## 功能介绍<a name="section57853128105524"></a>

该接口为扩展接口，用户在一个区域制作的私有镜像，可以通过跨Region复制镜像将镜像复制到其他区域，在其他区域发放相同类型的云服务器，帮助用户实现区域间的业务迁移。

该接口为异步接口，返回job\_id说明任务下发成功，查询异步任务状态，如果是success说明任务执行成功，如果是failed说明任务执行失败。

## 约束与限制<a name="section5429524792654"></a>

-   跨区域复制镜像的目的区域不能与镜像源区域相同。
-   加密镜像不支持跨区域复制。
-   跨区域复制镜像的大小限制如下：

    “华南-广州”、“华东-上海一”、“华东-上海二”和“华北-北京四”用于跨区域复制的镜像不能超过300GB；其他区域用于跨区域复制的镜像不能超过128GB。

-   跨区域复制镜像单租户并发复制不能超过5个私有镜像。
-   使用ISO文件创建的私有镜像不支持跨区域复制。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=CopyImageCrossRegion)中调试该接口。

## URI<a name="section30564347105524"></a>

POST /v1/cloudimages/\{image\_id\}/cross\_region\_copy

参数说明请参见[表1](#table51065259105524)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID。如何获取镜像ID，请参见查询镜像列表。|


## 请求消息<a name="section1218229105524"></a>

-   请求参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|name|是|String|镜像名称。name参数说明请参考镜像属性。|
|description|否|String|镜像描述信息。_description参数说明请参考镜像属性。支持字母、数字、中文等，不支持回车、<、>，长度不能超过1024个字符。默认为空。|
|region|是|String|目的区域的Region ID。如何获取Region ID列表，请参见“查询区域列表”。|
|project_name|是|String|目的区域的项目名称。|
|agency_name|是|String|委托名称。怎样创建IAM委托，请参见“如何创建IAM委托？”。|


-   请求样例

    ```
    POST https://{Endpoint}/v1/cloudimages/465076de-dc36-4aec-80f5-ef9d8009428f/cross_region_copy
    ```

    ```
    {
        "name":"test-copy-1001-4",
        "description":"test",
        "region":"region-1",
        "project_name":"region-1",
        "agency_name":"ims_copy_image"
    }
    ```


## 响应消息<a name="section32485736105524"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|job_id|String|异步任务ID。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    {
        "job_id": "edc89b490d7d4392898e19b2deb34797"
    }
    ```


## 返回值<a name="section40084941"></a>

-   正常

    200

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误，具体返回错误码请参错误码。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



