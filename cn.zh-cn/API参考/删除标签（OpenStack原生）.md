# 删除标签（OpenStack原生）<a name="ims_03_0713"></a>

## 功能介绍<a name="section18389930"></a>

该接口主要用于删除某个镜像的自定义标签，通过该接口，用户可以将私有镜像中一些不用的标签删除。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteTag)中调试该接口。

## URI<a name="section31291646"></a>

DELETE /v2/images/\{image\_id\}/tags/\{tag\}

参数说明请参见[表1](#table25869170205722)。

**表 1**  参数说明

<a name="table25869170205722"></a>
<table><thead align="left"><tr id="row8391193205722"><th class="cellrowborder" valign="top" width="18.60813918608139%" id="mcps1.2.5.1.1"><p id="p8598055205722"><a name="p8598055205722"></a><a name="p8598055205722"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.2"><p id="p25353829205722"><a name="p25353829205722"></a><a name="p25353829205722"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="19.778022197780224%" id="mcps1.2.5.1.3"><p id="p40394235205722"><a name="p40394235205722"></a><a name="p40394235205722"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="41.87581241875812%" id="mcps1.2.5.1.4"><p id="p50707602205722"><a name="p50707602205722"></a><a name="p50707602205722"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row13675089205722"><td class="cellrowborder" valign="top" width="18.60813918608139%" headers="mcps1.2.5.1.1 "><p id="p33940449205722"><a name="p33940449205722"></a><a name="p33940449205722"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p64821866205722"><a name="p64821866205722"></a><a name="p64821866205722"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.778022197780224%" headers="mcps1.2.5.1.3 "><p id="p16079763205722"><a name="p16079763205722"></a><a name="p16079763205722"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.87581241875812%" headers="mcps1.2.5.1.4 "><p id="p27392388205722"><a name="p27392388205722"></a><a name="p27392388205722"></a>镜像ID</p>
</td>
</tr>
<tr id="row45204903205722"><td class="cellrowborder" valign="top" width="18.60813918608139%" headers="mcps1.2.5.1.1 "><p id="p37718552205722"><a name="p37718552205722"></a><a name="p37718552205722"></a>tag</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p35303910205722"><a name="p35303910205722"></a><a name="p35303910205722"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="19.778022197780224%" headers="mcps1.2.5.1.3 "><p id="p41044472205722"><a name="p41044472205722"></a><a name="p41044472205722"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="41.87581241875812%" headers="mcps1.2.5.1.4 "><p id="p36267959205722"><a name="p36267959205722"></a><a name="p36267959205722"></a>镜像的tag。</p>
<p id="p58738960"><a name="p58738960"></a><a name="p58738960"></a>字符串中不能包含“=”。</p>
</td>
</tr>
</tbody>
</table>

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


