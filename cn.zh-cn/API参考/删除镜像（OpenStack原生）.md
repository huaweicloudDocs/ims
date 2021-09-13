# 删除镜像（OpenStack原生）<a name="ims_03_0706"></a>

## 功能介绍<a name="section24723024"></a>

该接口主要用于删除镜像，用户可以通过该接口将自己的私有镜像删除。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceDeleteImage)中调试该接口。

## URI<a name="section21180630"></a>

DELETE /v2/images/\{image\_id\}

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

<a name="table27262282"></a>
<table><thead align="left"><tr id="row27551015"><th class="cellrowborder" valign="top" width="22.720000000000002%" id="mcps1.2.5.1.1"><p id="p17039762"><a name="p17039762"></a><a name="p17039762"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.71%" id="mcps1.2.5.1.2"><p id="p38043494"><a name="p38043494"></a><a name="p38043494"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.49%" id="mcps1.2.5.1.3"><p id="p1119157921331"><a name="p1119157921331"></a><a name="p1119157921331"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="36.08%" id="mcps1.2.5.1.4"><p id="p61624137"><a name="p61624137"></a><a name="p61624137"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row25499238"><td class="cellrowborder" valign="top" width="22.720000000000002%" headers="mcps1.2.5.1.1 "><p id="p52172387"><a name="p52172387"></a><a name="p52172387"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="20.71%" headers="mcps1.2.5.1.2 "><p id="p65213800"><a name="p65213800"></a><a name="p65213800"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.49%" headers="mcps1.2.5.1.3 "><p id="p3410274521331"><a name="p3410274521331"></a><a name="p3410274521331"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="36.08%" headers="mcps1.2.5.1.4 "><p id="p47826462"><a name="p47826462"></a><a name="p47826462"></a>镜像ID</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section56407950"></a>

-   请求参数

    <a name="table53011268153646"></a>
    <table><thead align="left"><tr id="row8255548153646"><th class="cellrowborder" valign="top" width="19.6%" id="mcps1.1.5.1.1"><p id="p64719651153646"><a name="p64719651153646"></a><a name="p64719651153646"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.36%" id="mcps1.1.5.1.2"><p id="p7800370153646"><a name="p7800370153646"></a><a name="p7800370153646"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="19.1%" id="mcps1.1.5.1.3"><p id="p27850258153646"><a name="p27850258153646"></a><a name="p27850258153646"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.94%" id="mcps1.1.5.1.4"><p id="p41278443153646"><a name="p41278443153646"></a><a name="p41278443153646"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1512981414511"><td class="cellrowborder" valign="top" width="19.6%" headers="mcps1.1.5.1.1 "><p id="p913051418459"><a name="p913051418459"></a><a name="p913051418459"></a>delete_backup</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.36%" headers="mcps1.1.5.1.2 "><p id="p5160122504510"><a name="p5160122504510"></a><a name="p5160122504510"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="19.1%" headers="mcps1.1.5.1.3 "><p id="p10160202564511"><a name="p10160202564511"></a><a name="p10160202564511"></a>Boolean</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.94%" headers="mcps1.1.5.1.4 "><p id="p1813015143455"><a name="p1813015143455"></a><a name="p1813015143455"></a>取值为：true和false</p>
    <a name="ul119921040114519"></a><a name="ul119921040114519"></a><ul id="ul119921040114519"><li>true：表示删除整机镜像时，同时删除其关联的云服务器备份或云备份。</li><li>false：表示只删除整机镜像，不删除其关联的云服务器备份或云备份。</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

-   请求样例

    ```
    DELETE https://{Endpoint}/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba90
    ```

    ```
    {
        "delete_backup": true
    }
    ```


## 响应消息<a name="section37909503"></a>

-   响应参数

    无

-   响应样例

    ```
    STATUS CODE 204
    ```


## 返回值<a name="section5641212"></a>

-   正常

    204

-   异常

    <a name="table5314667917313"></a>
    <table><thead align="left"><tr id="row4648913117313"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p752327917313"><a name="p752327917313"></a><a name="p752327917313"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p540582617313"><a name="p540582617313"></a><a name="p540582617313"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3521879917313"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3415046017313"><a name="p3415046017313"></a><a name="p3415046017313"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1472385717313"><a name="p1472385717313"></a><a name="p1472385717313"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row5178178317313"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3357490117313"><a name="p3357490117313"></a><a name="p3357490117313"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p3521250017313"><a name="p3521250017313"></a><a name="p3521250017313"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row4847705217313"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3432710217313"><a name="p3432710217313"></a><a name="p3432710217313"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2903189317313"><a name="p2903189317313"></a><a name="p2903189317313"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row48061152191227"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p24571129191230"><a name="p24571129191230"></a><a name="p24571129191230"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p44104462191230"><a name="p44104462191230"></a><a name="p44104462191230"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row5996045217313"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2495845317313"><a name="p2495845317313"></a><a name="p2495845317313"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p836881417313"><a name="p836881417313"></a><a name="p836881417313"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row821047017313"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p6106831917313"><a name="p6106831917313"></a><a name="p6106831917313"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p4758680517313"><a name="p4758680517313"></a><a name="p4758680517313"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


