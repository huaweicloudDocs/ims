# 查询镜像列表视图（OpenStack原生）<a name="ims_03_0716"></a>

## 功能介绍<a name="section29906272"></a>

该接口主要用于查询镜像列表视图，通过该接口用户可以了解到镜像列表的详细情况和数据结构。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceListImageSchemas)中调试该接口。

## URI<a name="section720995"></a>

GET /v2/schemas/images

## 请求消息<a name="section6488958"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/schemas/images
    ```


## 响应消息<a name="section58400626"></a>

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
        "name": "images",
        "links": [
            {
                "href": "{first}",
                "rel": "first"
            },
            {
                "href": "{next}",
                "rel": "next"
            },
            {
                "href": "{schema}",
                "rel": "describedby"
            }
        ],
        "properties": {
            "images": {
                "items": {
                    "additionalProperties": {
                        "type": "String"
                    },
                    "name": "image",
                    "links": [
                        {
                            "href": "{self}",
                            "rel": "self"
                        },
                        {
                            "href": "{file}",
                            "rel": "enclosure"
                        },
                        {
                            "href": "{schema}",
                            "rel": "describedby"
                        }
                    ],
                    "properties": {
                        "status": {
                            "enum": [
                                "queued",
                                "saving",
                                "active",
                                "killed",
                                "deleted",
                                "pending_delete"
                            ],
                            "type": "string",
                            "description": "Status of the image (READ-ONLY)"
                        },
                        "tags": {
                            "items": {
                                "type": "string",
                                "maxLength": 255
                            },
                            "type": "array",
                            "description": "List of strings related to the image"
                        },
                        "kernel_id": {
                            "pattern": "^([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}$",
                            "type": "string",
                            "description": "ID of image stored in Glance that should be used as the kernel when booting an AMI-style image.",
                            "is_base": false
                        },
                        "container_format": {
                            "enum": [
                                "ami",
                                "ari",
                                "aki",
                                "bare",
                                "ovf",
                                "ova"
                            ],
                            "type": "string",
                            "description": "Format of the container"
                        },
                        "min_ram": {
                            "type": "integer",
                            "description": "Amount of ram (in MB) required to boot image."
                        },
                        "ramdisk_id": {
                            "pattern": "^([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}$",
                            "type": "string",
                            "description": "ID of image stored in Glance that should be used as the ramdisk when booting an AMI-style image.",
                            "is_base": false
                        },
                        "locations": {
                            "items": {
                                "required": [
                                    "url",
                                    "metadata"
                                ],
                                "type": "object",
                                "properties": {
                                    "url": {
                                        "type": "string",
                                        "maxLength": 255
                                    },
                                    "metadata": {
                                        "type": "object"
                                    }
                                }
                            },
                            "type": "array",
                            "description": "A set of URLs to access the image file kept in external store"
                        },
                        "visibility": {
                            "enum": [
                                "public",
                                "private"
                            ],
                            "type": "string",
                            "description": "Scope of image accessibility"
                        },
                        "updated_at": {
                            "type": "string",
                            "description": "Date and time of the last image modification (READ-ONLY)"
                        },
                        "owner": {
                            "type": "string",
                            "description": "Owner of the image",
                            "maxLength": 255
                        },
                        "file": {
                            "type": "string",
                            "description": "(READ-ONLY)"
                        },
                        "min_disk": {
                            "type": "integer",
                            "description": "Amount of disk space (in GB) required to boot image."
                        },
                        "virtual_size": {
                            "type": "integer",
                            "description": "Virtual size of image in bytes (READ-ONLY)"
                        },
                        "id": {
                            "pattern": "^([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}$",
                            "type": "string",
                            "description": "An identifier for the image"
                        },
                        "size": {
                            "type": "integer",
                            "description": "Size of image file in bytes (READ-ONLY)"
                        },
                        "instance_uuid": {
                            "type": "string",
                            "description": "ID of instance used to create this image.",
                            "is_base": false
                        },
                        "os_distro": {
                            "type": "string",
                            "description": "Common name of operating system distribution as specified in http://docs.openstack.org/trunk/openstack-compute/admin/content/adding-images.html",
                            "is_base": false
                        },
                        "name": {
                            "type": "string",
                            "description": "Descriptive name for the image",
                            "maxLength": 255
                        },
                        "checksum": {
                            "type": "string",
                            "description": "md5 hash of image contents. (READ-ONLY)",
                            "maxLength": 32
                        },
                        "created_at": {
                            "type": "string",
                            "description": "Date and time of image registration (READ-ONLY)"
                        },
                        "disk_format": {
                            "enum": [
                                "ami",
                                "ari",
                                "aki",
                                "vhd",
                                "vmdk",
                                "raw",
                                "qcow2",
                                "vdi",
                                "iso"
                            ],
                            "type": "string",
                            "description": "Format of the disk"
                        },
                        "os_version": {
                            "type": "string",
                            "description": "Operating system version as specified by the distributor",
                            "is_base": false
                        },
                        "protected": {
                            "type": "boolean",
                            "description": "If true, image will not be deletable."
                        },
                        "architecture": {
                            "type": "string",
                            "description": "Operating system architecture as specified in http://docs.openstack.org/trunk/openstack-compute/admin/content/adding-images.html",
                            "is_base": false
                        },
                        "direct_url": {
                            "type": "string",
                            "description": "URL to access the image file kept in external store (READ-ONLY)"
                        },
                        "self": {
                            "type": "string",
                            "description": "(READ-ONLY)"
                        },
                        "schema": {
                            "type": "string",
                            "description": "(READ-ONLY)"
                        }
                    }
                },
                "type": "array"
            },
            "schema": {
                "type": "string"
            },
            "next": {
                "type": "string"
            },
            "first": {
                "type": "string"
            }
        }
    }
    ```


## 返回值<a name="section55843593"></a>

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



