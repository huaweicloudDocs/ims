# Region内复制镜像<a name="ims_03_0627"></a>

## 功能介绍<a name="section57853128105524"></a>

该接口为扩展接口，主要用于用户将一个已有镜像复制为另一个镜像。复制镜像时，可以更改镜像的加密等属性，以满足不同的场景。

该接口为异步接口，返回job\_id说明任务下发成功，查询异步任务状态，如果是success说明任务执行成功，如果是failed说明任务执行失败。如何查询异步任务，请参见[异步任务查询](异步任务查询.md)。

## 约束与限制<a name="section183915210102"></a>

-   整机镜像不支持区域内复制。
-   使用ISO文件创建的私有镜像不支持区域内复制。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=CopyImageInRegion)中调试该接口。

## URI<a name="section30564347105524"></a>

POST /v1/cloudimages/\{image\_id\}/copy

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
|cmk_id|否|String|加密密钥。默认为空。|
|enterprise_project_id|否|String|表示当前镜像所属的企业项目。取值为0或无该值，表示属于default企业项目。取值为UUID，表示属于该UUID对应的企业项目。关于企业项目ID的获取及企业项目特性的详细信息，请参考“企业中心总览”。|


-   请求样例

    ```
    POST https://{Endpoint}/v1/cloudimages/465076de-dc36-4aec-80f5-ef9d8009428f/copy
    ```

    ```
    {
        "name": "ims_encrypted_copy3",
        "description": "test copy",
        "cmk_id": "bd66288c-9081-460a-8227-4cbd0c814cb4"
    }
    ```


## 响应消息<a name="section32485736105524"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|job_id|String|异步任务ID。详情请参见异步任务查询。|


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



