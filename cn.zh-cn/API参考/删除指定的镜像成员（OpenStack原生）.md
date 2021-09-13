# 删除指定的镜像成员（OpenStack原生）<a name="ims_03_0724"></a>

## 功能介绍<a name="section29995926"></a>

该接口用于取消对某个用户的镜像共享。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteImageMember)中调试该接口。

## URI<a name="section1527883"></a>

DELETE /v2/images/\{image\_id\}/members/\{member\_id\}

参数说明请参见[表1](#table6209770492526)。

**表 1**  参数说明

<a name="table6209770492526"></a>
<table><thead align="left"><tr id="row4392035892526"><th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.1"><p id="p77928492526"><a name="p77928492526"></a><a name="p77928492526"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.73%" id="mcps1.2.5.1.2"><p id="p6312205492526"><a name="p6312205492526"></a><a name="p6312205492526"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.919999999999998%" id="mcps1.2.5.1.3"><p id="p1261277392526"><a name="p1261277392526"></a><a name="p1261277392526"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40.61%" id="mcps1.2.5.1.4"><p id="p1500168892526"><a name="p1500168892526"></a><a name="p1500168892526"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row717722492526"><td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.1 "><p id="p4448425292526"><a name="p4448425292526"></a><a name="p4448425292526"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="18.73%" headers="mcps1.2.5.1.2 "><p id="p4645465392526"><a name="p4645465392526"></a><a name="p4645465392526"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p473051492526"><a name="p473051492526"></a><a name="p473051492526"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40.61%" headers="mcps1.2.5.1.4 "><p id="p4762733192526"><a name="p4762733192526"></a><a name="p4762733192526"></a>镜像ID</p>
</td>
</tr>
<tr id="row2599280292526"><td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.1 "><p id="p2504225092526"><a name="p2504225092526"></a><a name="p2504225092526"></a>member_id</p>
</td>
<td class="cellrowborder" valign="top" width="18.73%" headers="mcps1.2.5.1.2 "><p id="p1515635492526"><a name="p1515635492526"></a><a name="p1515635492526"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p1970513892526"><a name="p1970513892526"></a><a name="p1970513892526"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40.61%" headers="mcps1.2.5.1.4 "><p id="p5261235592526"><a name="p5261235592526"></a><a name="p5261235592526"></a>成员ID</p>
</td>
</tr>
</tbody>
</table>

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

    <a name="table2557613417418"></a>
    <table><thead align="left"><tr id="row2726860617418"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p6127347417418"><a name="p6127347417418"></a><a name="p6127347417418"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p6420439117418"><a name="p6420439117418"></a><a name="p6420439117418"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3317320517418"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p267505917418"><a name="p267505917418"></a><a name="p267505917418"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1535319317418"><a name="p1535319317418"></a><a name="p1535319317418"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row396101317418"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p5240662717418"><a name="p5240662717418"></a><a name="p5240662717418"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1707839817418"><a name="p1707839817418"></a><a name="p1707839817418"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row1948785517418"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3501244017418"><a name="p3501244017418"></a><a name="p3501244017418"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1743536117418"><a name="p1743536117418"></a><a name="p1743536117418"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row66661301191255"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p26317130191257"><a name="p26317130191257"></a><a name="p26317130191257"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p51312824191257"><a name="p51312824191257"></a><a name="p51312824191257"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row2270052117418"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2680288517418"><a name="p2680288517418"></a><a name="p2680288517418"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2355010217418"><a name="p2355010217418"></a><a name="p2355010217418"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row1062433417418"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p5526474517418"><a name="p5526474517418"></a><a name="p5526474517418"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p4725937317418"><a name="p4725937317418"></a><a name="p4725937317418"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


