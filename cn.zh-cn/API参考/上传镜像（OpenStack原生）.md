# 上传镜像（OpenStack原生）<a name="ims_03_0705"></a>

## 功能介绍<a name="section11046056154747"></a>

该接口用于上传用户本地的镜像文件到云平台。使用该接口上传镜像时，镜像文件大小需要小于2GB，超过2GB的镜像文件参考[注册镜像](注册镜像.md)进行操作。

了解更多关于使用外部文件创建镜像的相关内容，请参见“[通过外部镜像文件创建Windows系统盘镜像](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030713182.html)”、“[通过外部镜像文件创建Linux系统盘镜像](https://support.huaweicloud.com/usermanual-ims/zh-cn_topic_0030713191.html)”。

使用该接口上传镜像的具体步骤如下：

1.  准备待上传的镜像，支持的镜像格式：QCOW2、VMDK、VHD、RAW、VHDX、QED、VDI、QCOW、ZVHD2和ZVHD。
2.  <a name="li57474254155728"></a>使用[创建镜像元数据（OpenStack原生）](创建镜像元数据（OpenStack原生）.md)创建镜像元数据。调用成功后，保存该镜像的ID。
3.  使用[2](#li57474254155728)得到的镜像ID，上传支持格式的镜像文件。

## URI<a name="section66620681154747"></a>

PUT /v2/images/\{image\_id\}/file

参数说明请参见[表1](#table23910047154747)。

**表 1**  参数说明

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|image_id|是|String|镜像ID。image_id为用户调用创建镜像元数据接口所创建出来镜像的id，使用其他方式创建的镜像id会导致上传失败。上传接口调用成功后，请根据镜像id查询镜像的状态。镜像状态变为active表示镜像上传成功。|


## 请求消息<a name="section29704853154747"></a>

-   请求参数

|参数|是否必选|参数类型|描述|
|--|--|--|--|
|*image_file*|是|file|上传文件请求体，选择需要上传的本地文件|


-   请求样例

    ```
    PUT https://{Endpoint}/v2/images/84ac7f2b-bf19-4efb-86a0-b5be8771b476/file
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果使用curl命令方式调用接口，样例参考如下：
    >```
    >curl -i --insecure 'https://IP/v2/images/84ac7f2b-bf19-4efb-86a0-b5be8771b476/file' -X PUT -H "X-Auth-Token: $mytoken" -H "Content-Type:application/octet-stream" -T /mnt/userdisk/images/suse.zvhd
    >```


## 响应消息<a name="section42338041154747"></a>

-   响应参数

    无

-   响应样例

    ```
    HTTP/1.1 204
    ```


## 返回值<a name="section61463701154747"></a>

-   正常

    204

-   异常

|返回值|说明|
|--|--|
|400 Bad Request|请求错误，具体返回错误码请参错误码。|
|401 Unauthorized|鉴权失败。|
|403 Forbidden|没有操作权限。|
|404 Not Found|找不到资源。|
|409 Conflict|请求冲突。|
|500 System Error|系统错误。|



