# 查询版本列表（OpenStack原生）<a name="ims_03_0726"></a>

## 功能介绍<a name="section18441284152049"></a>

查询API的版本信息列表，包括API的版本兼容性、域名信息等。

## URI<a name="section21923693152049"></a>

GET /

## 请求消息<a name="section62484847152049"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/
    ```


## 响应消息<a name="section47461859152049"></a>

-   响应参数

|参数|参数类型|描述|
|--|--|--|
|versions|Array of objects|版本信息。详情请参见表1。|


    **表 1**  versions字段说明

|参数|参数类型|描述|
|--|--|--|
|status|String|接口状态。|
|id|String|接口ID。|
|links|Array of objects|自描述信息。详情请参见表2。|


    **表 2**  versions.links字段说明

|参数|参数类型|描述|
|--|--|--|
|href|String|域名。|
|rel|String|域名描述。|


-   响应样例

    ```
    STATUS CODE 300
    ```

    ```
    {
        "versions": [
            {
                "status": "CURRENT",
                "id": "v2.2",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v2/",
                        "rel": "self"
                    }
                ]
            },
            {
                "status": "SUPPORTED",
                "id": "v2.1",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v2/",
                        "rel": "self"
                    }
                ]
            },
            {
                "status": "SUPPORTED",
                "id": "v2.0",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v2/",
                        "rel": "self"
                    }
                ]
            },
            {
                "status": "DEPRECATED",
                "id": "v1.1",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v1/",
                        "rel": "self"
                    }
                ]
            },
            {
                "status": "DEPRECATED",
                "id": "v1.0",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v1/",
                        "rel": "self"
                    }
                ]
            }
        ]
    }
    ```


## 返回值<a name="section37588986152049"></a>

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



