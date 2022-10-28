# 查询镜像支持的OS列表<a name="ims_03_0610"></a>

## 功能介绍<a name="section1194520316464"></a>

查询当前区域弹性云服务器的OS兼容性列表。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=ListOsVersions)中调试该接口。

## URI<a name="section1594513117469"></a>

GET /v1/cloudimages/os\_version

**表 1**  查询参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|tag|否|String|OS的标签。根据标签值可以过滤查询指定特性的OS信息。取值范围：bms：表示该镜像支持BMS的os_version列表。uefi：支持UEFI启动方式的os_version列表。arm：显示基于arm架构的os_version列表。x86：显示基于x86架构的os_version列表。不带tag查询条件则默认查询当前region支持的所有的OS列表。|


## 请求消息<a name="section1394517316467"></a>

-   请求参数

    无

-   请求样例
    -   查询当前region支持的OS列表

        ```
        GET https://{Endpoint}/v1/cloudimages/os_version
        ```

    -   根据过滤条件查询OS列表

        ```
        GET https://{Endpoint}/v1/cloudimages/os_version?tag=kvm&tag=uefi
        ```



## 响应消息<a name="section639632154617"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|*[数组]*|Array of objects|详情请参见表2。|


    **表 2** _\[数组\]_字段说明

|参数|参数类型|描述|
|--|--|--|
|platform|String|操作系统平台。|
|version_list|Array of objects|返回的操作系统详情。具体请参见表3。|


    **表 3** _\[数组\]_.version\_list字段数据结构说明

|参数|参数类型|描述|
|--|--|--|
|platform|String|操作系统平台。|
|os_version_key|String|操作系统key值。默认取os_version的值为key值。|
|os_version|String|操作系统完整信息。|
|os_bit|Integer|操作系统的位数。|
|os_type|String|操作系统的类型。|


-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    [
        {
            "platform": "SUSE",
            "version_list": [
                {
                    "platform": "SUSE",
                    "os_version_key": "SUSE Linux Enterprise Server 15 64bit",
                    "os_version": "SUSE Linux Enterprise Server 15 64bit",
                    "os_bit": 64,
                    "os_type": "Linux"
                },
                {
                    "platform": "SUSE",
                    "os_version_key": "SUSE Linux Enterprise Server 12 SP3 64bit",
                    "os_version": "SUSE Linux Enterprise Server 12 SP3 64bit",
                    "os_bit": 64,
                    "os_type": "Linux"
                }
            ]
        },
        {
            "platform": "Other",
            "version_list": [
                {
                    "platform": "Other",
                    "os_version_key": "Other(32 bit)",
                    "os_version": "Other(32 bit)",
                    "os_bit": 32,
                    "os_type": "Linux"
                }
            ]
        }
    ]
    ```


## 返回值<a name="section539103214611"></a>

-   正常

    200

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误，具体返回错误码请参见错误码。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|500 Internal Server Error|服务内部错误。|
|503 Service Unavailable|服务不可用。|



