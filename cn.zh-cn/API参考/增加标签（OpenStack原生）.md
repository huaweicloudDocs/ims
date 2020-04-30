# 增加标签（OpenStack原生）<a name="ims_03_0712"></a>

## 功能介绍<a name="section43944024"></a>

该接口主要用于为某个镜像添加一个自定义标签。通过自定义标签，用户可以将镜像进行分类。

## URI<a name="section59951903"></a>

PUT /v2/images/\{image\_id\}/tags/\{tag\}

参数说明请参见[表1](#table58396974)。

**表 1**  参数说明

<a name="table58396974"></a>
<table><thead align="left"><tr id="row52161898"><th class="cellrowborder" valign="top" width="18.60813918608139%" id="mcps1.2.5.1.1"><p id="p64364196"><a name="p64364196"></a><a name="p64364196"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="19.73802619738026%" id="mcps1.2.5.1.2"><p id="p40455902205623"><a name="p40455902205623"></a><a name="p40455902205623"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="17.74822517748225%" id="mcps1.2.5.1.3"><p id="p46117407"><a name="p46117407"></a><a name="p46117407"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.90560943905609%" id="mcps1.2.5.1.4"><p id="p44522499"><a name="p44522499"></a><a name="p44522499"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row49552630"><td class="cellrowborder" valign="top" width="18.60813918608139%" headers="mcps1.2.5.1.1 "><p id="p54340131"><a name="p54340131"></a><a name="p54340131"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p15622373205623"><a name="p15622373205623"></a><a name="p15622373205623"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.74822517748225%" headers="mcps1.2.5.1.3 "><p id="p39474480"><a name="p39474480"></a><a name="p39474480"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.90560943905609%" headers="mcps1.2.5.1.4 "><p id="p43316293"><a name="p43316293"></a><a name="p43316293"></a>镜像ID</p>
</td>
</tr>
<tr id="row54302323"><td class="cellrowborder" valign="top" width="18.60813918608139%" headers="mcps1.2.5.1.1 "><p id="p36412008"><a name="p36412008"></a><a name="p36412008"></a>tag</p>
</td>
<td class="cellrowborder" valign="top" width="19.73802619738026%" headers="mcps1.2.5.1.2 "><p id="p47312118205623"><a name="p47312118205623"></a><a name="p47312118205623"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="17.74822517748225%" headers="mcps1.2.5.1.3 "><p id="p63691513"><a name="p63691513"></a><a name="p63691513"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.90560943905609%" headers="mcps1.2.5.1.4 "><p id="p75636161112"><a name="p75636161112"></a><a name="p75636161112"></a>新增的tag。</p>
<p id="p3391142192115"><a name="p3391142192115"></a><a name="p3391142192115"></a>字符串中不能包含“=”。</p>
<div class="note" id="note1350761815387"><a name="note1350761815387"></a><a name="note1350761815387"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p550721883817"><a name="p550721883817"></a><a name="p550721883817"></a>该接口只能添加标签键，如果需要添加标签值，请使用接口PUT /v1/cloudimages/tags ，详情请参考<a href="增加或修改标签.md">增加或修改标签</a>。</p>
</div></div>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section2696221"></a>

-   请求参数

    无

-   请求样例

    ```
    PUT https://{Endpoint}/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba90/tags/aaaa
    ```


## 响应消息<a name="section24265995"></a>

-   响应参数

    无

-   响应样例

    ```
    STATUS CODE 204
    ```


## 返回值<a name="section17067371"></a>

-   正常

    204

-   异常

    <a name="table642803117411"></a>
    <table><thead align="left"><tr id="row109645217411"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p2170376317411"><a name="p2170376317411"></a><a name="p2170376317411"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p1317436717411"><a name="p1317436717411"></a><a name="p1317436717411"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row6049076717411"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p80506717411"><a name="p80506717411"></a><a name="p80506717411"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6521049217411"><a name="p6521049217411"></a><a name="p6521049217411"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row5002352417411"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2537366317411"><a name="p2537366317411"></a><a name="p2537366317411"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p4200083517411"><a name="p4200083517411"></a><a name="p4200083517411"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row4246319517411"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p1696676617411"><a name="p1696676617411"></a><a name="p1696676617411"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p3213081417411"><a name="p3213081417411"></a><a name="p3213081417411"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row22446538192234"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2466565192236"><a name="p2466565192236"></a><a name="p2466565192236"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p65574046192236"><a name="p65574046192236"></a><a name="p65574046192236"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row2074187217411"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p237005317411"><a name="p237005317411"></a><a name="p237005317411"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p5775661917411"><a name="p5775661917411"></a><a name="p5775661917411"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row5004752817411"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2731794517411"><a name="p2731794517411"></a><a name="p2731794517411"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6526996817411"><a name="p6526996817411"></a><a name="p6526996817411"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


