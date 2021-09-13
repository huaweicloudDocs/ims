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

    <a name="table4863803311445"></a>
    <table><thead align="left"><tr id="row3629282211445"><th class="cellrowborder" valign="top" width="28.27%" id="mcps1.1.4.1.1"><p id="p5403745111445"><a name="p5403745111445"></a><a name="p5403745111445"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="26.290000000000003%" id="mcps1.1.4.1.2"><p id="p5399240419951"><a name="p5399240419951"></a><a name="p5399240419951"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.440000000000005%" id="mcps1.1.4.1.3"><p id="p1495742511445"><a name="p1495742511445"></a><a name="p1495742511445"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3527303211445"><td class="cellrowborder" valign="top" width="28.27%" headers="mcps1.1.4.1.1 "><p id="p3854335911445"><a name="p3854335911445"></a><a name="p3854335911445"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.290000000000003%" headers="mcps1.1.4.1.2 "><p id="p4358420519951"><a name="p4358420519951"></a><a name="p4358420519951"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.440000000000005%" headers="mcps1.1.4.1.3 "><p id="p3500440311445"><a name="p3500440311445"></a><a name="p3500440311445"></a>视图名称。</p>
    </td>
    </tr>
    <tr id="row4660417511445"><td class="cellrowborder" valign="top" width="28.27%" headers="mcps1.1.4.1.1 "><p id="p1684183211445"><a name="p1684183211445"></a><a name="p1684183211445"></a>links</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.290000000000003%" headers="mcps1.1.4.1.2 "><p id="p4065973219951"><a name="p4065973219951"></a><a name="p4065973219951"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.440000000000005%" headers="mcps1.1.4.1.3 "><p id="p2201118611445"><a name="p2201118611445"></a><a name="p2201118611445"></a>视图链接。</p>
    <p id="p123432895413"><a name="p123432895413"></a><a name="p123432895413"></a>详情请参见<a href="#table15641103183416">表1</a>。</p>
    </td>
    </tr>
    <tr id="row6388295311445"><td class="cellrowborder" valign="top" width="28.27%" headers="mcps1.1.4.1.1 "><p id="p713670311445"><a name="p713670311445"></a><a name="p713670311445"></a>properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.290000000000003%" headers="mcps1.1.4.1.2 "><p id="p510402419951"><a name="p510402419951"></a><a name="p510402419951"></a>Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.440000000000005%" headers="mcps1.1.4.1.3 "><p id="p8616104025420"><a name="p8616104025420"></a><a name="p8616104025420"></a>镜像属性说明，主要是对基础属性的说明，包含每个属性的取值类型，用途。</p>
    <p id="p4120204111445"><a name="p4120204111445"></a><a name="p4120204111445"></a>具体参数说明可参考<a href="镜像属性.md">镜像属性</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 1**  links字段说明

    <a name="table15641103183416"></a>
    <table><thead align="left"><tr id="row136411132345"><th class="cellrowborder" valign="top" width="28.277172282771723%" id="mcps1.2.4.1.1"><p id="p136411433347"><a name="p136411433347"></a><a name="p136411433347"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="26.4973502649735%" id="mcps1.2.4.1.2"><p id="p12641193183412"><a name="p12641193183412"></a><a name="p12641193183412"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.22547745225477%" id="mcps1.2.4.1.3"><p id="p164120311348"><a name="p164120311348"></a><a name="p164120311348"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row4641634345"><td class="cellrowborder" valign="top" width="28.277172282771723%" headers="mcps1.2.4.1.1 "><p id="p126411432347"><a name="p126411432347"></a><a name="p126411432347"></a>href</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.4973502649735%" headers="mcps1.2.4.1.2 "><p id="p1864133173419"><a name="p1864133173419"></a><a name="p1864133173419"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.22547745225477%" headers="mcps1.2.4.1.3 "><p id="p16411373420"><a name="p16411373420"></a><a name="p16411373420"></a>域名。</p>
    </td>
    </tr>
    <tr id="row146411238348"><td class="cellrowborder" valign="top" width="28.277172282771723%" headers="mcps1.2.4.1.1 "><p id="p156421039346"><a name="p156421039346"></a><a name="p156421039346"></a>rel</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.4973502649735%" headers="mcps1.2.4.1.2 "><p id="p196421736343"><a name="p196421736343"></a><a name="p196421736343"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.22547745225477%" headers="mcps1.2.4.1.3 "><p id="p1164263163416"><a name="p1164263163416"></a><a name="p1164263163416"></a>域名描述。</p>
    </td>
    </tr>
    </tbody>
    </table>

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

    <a name="table512644917454"></a>
    <table><thead align="left"><tr id="row5075107217454"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p1719616917454"><a name="p1719616917454"></a><a name="p1719616917454"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p5071248317454"><a name="p5071248317454"></a><a name="p5071248317454"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1407048617454"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p6596756117454"><a name="p6596756117454"></a><a name="p6596756117454"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p4177219617454"><a name="p4177219617454"></a><a name="p4177219617454"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row4040544817454"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p5161589217454"><a name="p5161589217454"></a><a name="p5161589217454"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2013769117454"><a name="p2013769117454"></a><a name="p2013769117454"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row4702149717454"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p5064493517454"><a name="p5064493517454"></a><a name="p5064493517454"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p859904517454"><a name="p859904517454"></a><a name="p859904517454"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row27405030192213"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p15819393192215"><a name="p15819393192215"></a><a name="p15819393192215"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6302489192215"><a name="p6302489192215"></a><a name="p6302489192215"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row1028254117454"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2757951117454"><a name="p2757951117454"></a><a name="p2757951117454"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1934790917454"><a name="p1934790917454"></a><a name="p1934790917454"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row3991345717454"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p1176460917454"><a name="p1176460917454"></a><a name="p1176460917454"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1340929017454"><a name="p1340929017454"></a><a name="p1340929017454"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


