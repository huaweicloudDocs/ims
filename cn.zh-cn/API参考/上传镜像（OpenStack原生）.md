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

<a name="table23910047154747"></a>
<table><thead align="left"><tr id="row24965460154747"><th class="cellrowborder" valign="top" width="19.62%" id="mcps1.2.5.1.1"><p id="p8936346154747"><a name="p8936346154747"></a><a name="p8936346154747"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.279999999999998%" id="mcps1.2.5.1.2"><p id="p4072498116916"><a name="p4072498116916"></a><a name="p4072498116916"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.299999999999997%" id="mcps1.2.5.1.3"><p id="p52755425154747"><a name="p52755425154747"></a><a name="p52755425154747"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="44.800000000000004%" id="mcps1.2.5.1.4"><p id="p57477321154747"><a name="p57477321154747"></a><a name="p57477321154747"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row25151394154747"><td class="cellrowborder" valign="top" width="19.62%" headers="mcps1.2.5.1.1 "><p id="p23996995154747"><a name="p23996995154747"></a><a name="p23996995154747"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="18.279999999999998%" headers="mcps1.2.5.1.2 "><p id="p1038913616916"><a name="p1038913616916"></a><a name="p1038913616916"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.299999999999997%" headers="mcps1.2.5.1.3 "><p id="p64708437154747"><a name="p64708437154747"></a><a name="p64708437154747"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="44.800000000000004%" headers="mcps1.2.5.1.4 "><p id="p54354750154747"><a name="p54354750154747"></a><a name="p54354750154747"></a>镜像ID。</p>
<a name="ul2091361694"></a><a name="ul2091361694"></a><ul id="ul2091361694"><li>image_id为用户调用创建镜像元数据接口所创建出来镜像的id，使用其他方式创建的镜像id会导致上传失败。</li><li>上传接口调用成功后，请根据镜像id查询镜像的状态。镜像状态变为active表示镜像上传成功。</li></ul>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section29704853154747"></a>

-   请求参数

    <a name="table1589154165910"></a>
    <table><thead align="left"><tr id="row16589954125913"><th class="cellrowborder" valign="top" width="16.61%" id="mcps1.1.5.1.1"><p id="p209573120020"><a name="p209573120020"></a><a name="p209573120020"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="15.06%" id="mcps1.1.5.1.2"><p id="p18957511209"><a name="p18957511209"></a><a name="p18957511209"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="15.299999999999999%" id="mcps1.1.5.1.3"><p id="p59571012008"><a name="p59571012008"></a><a name="p59571012008"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.03%" id="mcps1.1.5.1.4"><p id="p89571711901"><a name="p89571711901"></a><a name="p89571711901"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15891549597"><td class="cellrowborder" valign="top" width="16.61%" headers="mcps1.1.5.1.1 "><p id="p75891554165913"><a name="p75891554165913"></a><a name="p75891554165913"></a><em id="i207861278115"><a name="i207861278115"></a><a name="i207861278115"></a>image_file</em></p>
    </td>
    <td class="cellrowborder" valign="top" width="15.06%" headers="mcps1.1.5.1.2 "><p id="p18589654135916"><a name="p18589654135916"></a><a name="p18589654135916"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="15.299999999999999%" headers="mcps1.1.5.1.3 "><p id="p658925419599"><a name="p658925419599"></a><a name="p658925419599"></a>file</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.03%" headers="mcps1.1.5.1.4 "><p id="p115891854145911"><a name="p115891854145911"></a><a name="p115891854145911"></a>上传文件请求体，选择需要上传的本地文件</p>
    </td>
    </tr>
    </tbody>
    </table>

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

    <a name="table61689654164325"></a>
    <table><thead align="left"><tr id="row43263384164325"><th class="cellrowborder" valign="top" width="38.080000000000005%" id="mcps1.1.3.1.1"><p id="p14673233164325"><a name="p14673233164325"></a><a name="p14673233164325"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="61.919999999999995%" id="mcps1.1.3.1.2"><p id="p47681194164325"><a name="p47681194164325"></a><a name="p47681194164325"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row36971467164325"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p41898845164325"><a name="p41898845164325"></a><a name="p41898845164325"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p38363271164325"><a name="p38363271164325"></a><a name="p38363271164325"></a>请求错误，具体返回错误码请参<a href="错误码.md">错误码</a>。</p>
    </td>
    </tr>
    <tr id="row20417266164325"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p43185862164325"><a name="p43185862164325"></a><a name="p43185862164325"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p8393897164325"><a name="p8393897164325"></a><a name="p8393897164325"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row8436217164325"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p12244985164325"><a name="p12244985164325"></a><a name="p12244985164325"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p52319709164325"><a name="p52319709164325"></a><a name="p52319709164325"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row1115336164325"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p23233406164325"><a name="p23233406164325"></a><a name="p23233406164325"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p2857740164325"><a name="p2857740164325"></a><a name="p2857740164325"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row33911260174644"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p33585825174654"><a name="p33585825174654"></a><a name="p33585825174654"></a>409 Conflict</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p36097324174654"><a name="p36097324174654"></a><a name="p36097324174654"></a>请求冲突。</p>
    </td>
    </tr>
    <tr id="row60371567174640"><td class="cellrowborder" valign="top" width="38.080000000000005%" headers="mcps1.1.3.1.1 "><p id="p8274976174654"><a name="p8274976174654"></a><a name="p8274976174654"></a>500 System Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="61.919999999999995%" headers="mcps1.1.3.1.2 "><p id="p66293315174654"><a name="p66293315174654"></a><a name="p66293315174654"></a>系统错误。</p>
    </td>
    </tr>
    </tbody>
    </table>


