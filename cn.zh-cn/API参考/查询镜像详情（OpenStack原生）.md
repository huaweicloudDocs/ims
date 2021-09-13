# 查询镜像详情（OpenStack原生）<a name="ims_03_0703"></a>

## 功能介绍<a name="section39958021"></a>

查询单个镜像详情，用户可以通过该接口查询单个私有或者公共镜像的详情。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceShowImage)中调试该接口。

## URI<a name="section24077873"></a>

GET /v2/images/\{image\_id\}

参数说明请参见[表1](#table37590215162351)。

**表 1**  参数说明

<a name="table37590215162351"></a>
<table><thead align="left"><tr id="row14906674162351"><th class="cellrowborder" valign="top" width="22.81771822817718%" id="mcps1.2.5.1.1"><p id="p66589937162351"><a name="p66589937162351"></a><a name="p66589937162351"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22.897710228977104%" id="mcps1.2.5.1.2"><p id="p25075841162351"><a name="p25075841162351"></a><a name="p25075841162351"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="23.45765423457654%" id="mcps1.2.5.1.3"><p id="p3182134421246"><a name="p3182134421246"></a><a name="p3182134421246"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="30.826917308269174%" id="mcps1.2.5.1.4"><p id="p17877258162351"><a name="p17877258162351"></a><a name="p17877258162351"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38771763162351"><td class="cellrowborder" valign="top" width="22.81771822817718%" headers="mcps1.2.5.1.1 "><p id="p53505060162351"><a name="p53505060162351"></a><a name="p53505060162351"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="22.897710228977104%" headers="mcps1.2.5.1.2 "><p id="p38942598162351"><a name="p38942598162351"></a><a name="p38942598162351"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="23.45765423457654%" headers="mcps1.2.5.1.3 "><p id="p2739208421246"><a name="p2739208421246"></a><a name="p2739208421246"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.2.5.1.4 "><p id="p233856162351"><a name="p233856162351"></a><a name="p233856162351"></a>镜像ID</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section15374270"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images/33ad552d-1149-471c-8190-ff6776174a00
    ```


## 响应消息<a name="section4150710"></a>

-   响应参数

    <a name="table3940930519484"></a>
    <table><thead align="left"><tr id="row5108650619484"><th class="cellrowborder" valign="top" width="25.27%" id="mcps1.1.4.1.1"><p id="p4436630719484"><a name="p4436630719484"></a><a name="p4436630719484"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.580000000000002%" id="mcps1.1.4.1.2"><p id="p3690111319484"><a name="p3690111319484"></a><a name="p3690111319484"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.15%" id="mcps1.1.4.1.3"><p id="p3620014719484"><a name="p3620014719484"></a><a name="p3620014719484"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row4653077719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1089662919484"><a name="p1089662919484"></a><a name="p1089662919484"></a>file</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1021172419484"><a name="p1021172419484"></a><a name="p1021172419484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2184333619484"><a name="p2184333619484"></a><a name="p2184333619484"></a>镜像文件下载和上传链接。</p>
    </td>
    </tr>
    <tr id="row6237230419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1899183819484"><a name="p1899183819484"></a><a name="p1899183819484"></a>owner</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p6194387619484"><a name="p6194387619484"></a><a name="p6194387619484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5139805919484"><a name="p5139805919484"></a><a name="p5139805919484"></a>镜像属于哪个租户。</p>
    </td>
    </tr>
    <tr id="row5992935019484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2243918519484"><a name="p2243918519484"></a><a name="p2243918519484"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p563467219484"><a name="p563467219484"></a><a name="p563467219484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5375527619484"><a name="p5375527619484"></a><a name="p5375527619484"></a>镜像ID。</p>
    </td>
    </tr>
    <tr id="row1403543619484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p6312849319484"><a name="p6312849319484"></a><a name="p6312849319484"></a>size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1313430319484"><a name="p1313430319484"></a><a name="p1313430319484"></a>Long</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5724560919484"><a name="p5724560919484"></a><a name="p5724560919484"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row4544843919484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p5744495319484"><a name="p5744495319484"></a><a name="p5744495319484"></a>self</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2252964019484"><a name="p2252964019484"></a><a name="p2252964019484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1296154719484"><a name="p1296154719484"></a><a name="p1296154719484"></a>镜像链接信息。</p>
    </td>
    </tr>
    <tr id="row4954506419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p5372723719484"><a name="p5372723719484"></a><a name="p5372723719484"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p5693892219484"><a name="p5693892219484"></a><a name="p5693892219484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p4864998419484"><a name="p4864998419484"></a><a name="p4864998419484"></a>镜像视图。</p>
    </td>
    </tr>
    <tr id="row3519667719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3235856619484"><a name="p3235856619484"></a><a name="p3235856619484"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p379822119484"><a name="p379822119484"></a><a name="p379822119484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p32131061155224"><a name="p32131061155224"></a><a name="p32131061155224"></a>镜像状态。取值如下：</p>
    <a name="ul43292299155227"></a><a name="ul43292299155227"></a><ul id="ul43292299155227"><li>queued：表示镜像元数据已经创建成功，等待上传镜像文件。</li><li>saving：表示镜像正在上传文件到后端存储。</li><li>deleted：表示镜像已经删除。</li><li>killed：表示镜像上传错误。</li><li>active：表示镜像可以正常使用。</li></ul>
    </td>
    </tr>
    <tr id="row1743970919484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p333030119484"><a name="p333030119484"></a><a name="p333030119484"></a>tags</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p131897419484"><a name="p131897419484"></a><a name="p131897419484"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3972807119484"><a name="p3972807119484"></a><a name="p3972807119484"></a>镜像标签列表，提供用户可以自定义管理私有镜像的能力。用户可以通过镜像标签接口为每个镜像增加不同的标签，在查询接口中可以根据标签进行过滤。</p>
    </td>
    </tr>
    <tr id="row2200832719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3784404819484"><a name="p3784404819484"></a><a name="p3784404819484"></a>visibility</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4546904619484"><a name="p4546904619484"></a><a name="p4546904619484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p152431834103310"><a name="p152431834103310"></a><a name="p152431834103310"></a>是否被其他租户可见，取值如下：</p>
    <a name="ul17437224348"></a><a name="ul17437224348"></a><ul id="ul17437224348"><li>private：私有镜像</li><li>public：公共镜像</li><li>shared：共享镜像</li></ul>
    </td>
    </tr>
    <tr id="row6226467419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1027383819484"><a name="p1027383819484"></a><a name="p1027383819484"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2687454619484"><a name="p2687454619484"></a><a name="p2687454619484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2935464719484"><a name="p2935464719484"></a><a name="p2935464719484"></a>镜像名称。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row6286523719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p5891947019484"><a name="p5891947019484"></a><a name="p5891947019484"></a>checksum</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p774777119484"><a name="p774777119484"></a><a name="p774777119484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2358973319484"><a name="p2358973319484"></a><a name="p2358973319484"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row984493719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p5924239319484"><a name="p5924239319484"></a><a name="p5924239319484"></a>protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p3390450119484"><a name="p3390450119484"></a><a name="p3390450119484"></a>Boolean</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p6191008619484"><a name="p6191008619484"></a><a name="p6191008619484"></a>是否是受保护的，受保护的镜像不允许删除。取值为true或false。</p>
    </td>
    </tr>
    <tr id="row2031987019484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3529679319484"><a name="p3529679319484"></a><a name="p3529679319484"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4046799719484"><a name="p4046799719484"></a><a name="p4046799719484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5668228819484"><a name="p5668228819484"></a><a name="p5668228819484"></a>容器类型。</p>
    </td>
    </tr>
    <tr id="row4037855219484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p4943728819484"><a name="p4943728819484"></a><a name="p4943728819484"></a>min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4499737219484"><a name="p4499737219484"></a><a name="p4499737219484"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2090850919484"><a name="p2090850919484"></a><a name="p2090850919484"></a>镜像运行最小内存，单位为MB。取值参考<span id="text1636316313480"><a name="text1636316313480"></a><a name="text1636316313480"></a></span><span id="text1885219464811"><a name="text1885219464811"></a><a name="text1885219464811"></a>云服务器</span>规格限制，一般设置为0。</p>
    <p id="p574912347473"><a name="p574912347473"></a><a name="p574912347473"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
    </td>
    </tr>
    <tr id="row19560143913613"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p564272999235"><a name="p564272999235"></a><a name="p564272999235"></a>max_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p470176959235"><a name="p470176959235"></a><a name="p470176959235"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p503369709235"><a name="p503369709235"></a><a name="p503369709235"></a>镜像支持的最大内存，单位为MB。取值可以参考<span id="text818523316267"><a name="text818523316267"></a><a name="text818523316267"></a></span><span id="text518503312612"><a name="text518503312612"></a><a name="text518503312612"></a>云服务器</span>规格限制，一般不设置。</p>
    <p id="p490625184916"><a name="p490625184916"></a><a name="p490625184916"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
    </td>
    </tr>
    <tr id="row5395885319484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p859097919484"><a name="p859097919484"></a><a name="p859097919484"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2478073819484"><a name="p2478073819484"></a><a name="p2478073819484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p6108279419484"><a name="p6108279419484"></a><a name="p6108279419484"></a>更新时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row1287423619484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3618021119484"><a name="p3618021119484"></a><a name="p3618021119484"></a>__os_bit</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4491600719484"><a name="p4491600719484"></a><a name="p4491600719484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1431795119484"><a name="p1431795119484"></a><a name="p1431795119484"></a>操作系统位数，一般取值为“32”或者“64”。</p>
    </td>
    </tr>
    <tr id="row6175270019484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3591283819484"><a name="p3591283819484"></a><a name="p3591283819484"></a>__os_version</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2325879319484"><a name="p2325879319484"></a><a name="p2325879319484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p491406019484"><a name="p491406019484"></a><a name="p491406019484"></a>操作系统具体版本。</p>
    </td>
    </tr>
    <tr id="row4422654119484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2558005119484"><a name="p2558005119484"></a><a name="p2558005119484"></a>__description</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p5871828719484"><a name="p5871828719484"></a><a name="p5871828719484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5856077419484"><a name="p5856077419484"></a><a name="p5856077419484"></a>镜像描述信息。_description参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row5728492419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p956729019484"><a name="p956729019484"></a><a name="p956729019484"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p3675300019484"><a name="p3675300019484"></a><a name="p3675300019484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2420299019484"><a name="p2420299019484"></a><a name="p2420299019484"></a>镜像的格式，目前支持vhd、zvhd、raw、qcow2。默认值是vhd。</p>
    </td>
    </tr>
    <tr id="row1650032219484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p6145769619484"><a name="p6145769619484"></a><a name="p6145769619484"></a>__isregistered</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1201748319484"><a name="p1201748319484"></a><a name="p1201748319484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3389204219484"><a name="p3389204219484"></a><a name="p3389204219484"></a>是否是注册过的镜像，取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row3659292519484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1123691819484"><a name="p1123691819484"></a><a name="p1123691819484"></a>__platform</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p3777512719484"><a name="p3777512719484"></a><a name="p3777512719484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3988644119484"><a name="p3988644119484"></a><a name="p3988644119484"></a>镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。</p>
    </td>
    </tr>
    <tr id="row2343365119484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1907761719484"><a name="p1907761719484"></a><a name="p1907761719484"></a>__os_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p178315519484"><a name="p178315519484"></a><a name="p178315519484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1021789019484"><a name="p1021789019484"></a><a name="p1021789019484"></a>操作系统类型，目前取值Linux、Windows、Other。</p>
    </td>
    </tr>
    <tr id="row91509321512"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1784710241674"><a name="p1784710241674"></a><a name="p1784710241674"></a>__system__cmkid</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p6847152417713"><a name="p6847152417713"></a><a name="p6847152417713"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p28479241671"><a name="p28479241671"></a><a name="p28479241671"></a>加密镜像所使用的密钥ID。</p>
    </td>
    </tr>
    <tr id="row2485214919484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p6686709019484"><a name="p6686709019484"></a><a name="p6686709019484"></a>min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4752519919484"><a name="p4752519919484"></a><a name="p4752519919484"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p60826909104315"><a name="p60826909104315"></a><a name="p60826909104315"></a>镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。</p>
    </td>
    </tr>
    <tr id="row1769644219484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2412566319484"><a name="p2412566319484"></a><a name="p2412566319484"></a>virtual_env_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p802166419484"><a name="p802166419484"></a><a name="p802166419484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p125511012134911"><a name="p125511012134911"></a><a name="p125511012134911"></a>镜像使用环境类型：FusionCompute、Ironic、DataImage、IsoImage。</p>
    <a name="ul15999422124917"></a><a name="ul15999422124917"></a><ul id="ul15999422124917"><li>如果是<span id="text919452512486"><a name="text919452512486"></a><a name="text919452512486"></a></span><span id="text17194625114817"><a name="text17194625114817"></a><a name="text17194625114817"></a>云服务器</span>镜像（即系统盘镜像），则取值为FusionCompute。</li><li>如果是数据卷镜像，则取值为DataImage。</li><li>如果是<span id="text9788103710480"><a name="text9788103710480"></a><a name="text9788103710480"></a></span><span id="text11464639144812"><a name="text11464639144812"></a><a name="text11464639144812"></a>裸金属服务器</span>镜像，则取值为Ironic。</li><li>如果是ISO镜像，则取值是IsoImage。</li></ul>
    </td>
    </tr>
    <tr id="row932252719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1692720719484"><a name="p1692720719484"></a><a name="p1692720719484"></a>__image_source_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2892650319484"><a name="p2892650319484"></a><a name="p2892650319484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p6134541619484"><a name="p6134541619484"></a><a name="p6134541619484"></a>镜像后端存储类型，目前只支持uds。</p>
    </td>
    </tr>
    <tr id="row1523783619484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2630521719484"><a name="p2630521719484"></a><a name="p2630521719484"></a>__imagetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p5034781819484"><a name="p5034781819484"></a><a name="p5034781819484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p28701642133010"><a name="p28701642133010"></a><a name="p28701642133010"></a>镜像类型，目前支持以下类型：</p>
    <a name="ul387034210305"></a><a name="ul387034210305"></a><ul id="ul387034210305"><li>公共镜像：gold</li><li>私有镜像：private</li><li>共享镜像：shared</li></ul>
    </td>
    </tr>
    <tr id="row6211992119484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p6565767619484"><a name="p6565767619484"></a><a name="p6565767619484"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1667154419484"><a name="p1667154419484"></a><a name="p1667154419484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p821782019484"><a name="p821782019484"></a><a name="p821782019484"></a>创建时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row685152319484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1810251119484"><a name="p1810251119484"></a><a name="p1810251119484"></a>virtual_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p5701732019484"><a name="p5701732019484"></a><a name="p5701732019484"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p5500021319484"><a name="p5500021319484"></a><a name="p5500021319484"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row1054514319484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p4885024319484"><a name="p4885024319484"></a><a name="p4885024319484"></a>__originalimagename</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p6455557119484"><a name="p6455557119484"></a><a name="p6455557119484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p6161873519484"><a name="p6161873519484"></a><a name="p6161873519484"></a>父镜像ID。</p>
    <p id="p1769771019484"><a name="p1769771019484"></a><a name="p1769771019484"></a>公共镜像或通过文件创建的私有镜像，取值为空。</p>
    </td>
    </tr>
    <tr id="row2506166419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1672894219484"><a name="p1672894219484"></a><a name="p1672894219484"></a>__backup_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1286707219484"><a name="p1286707219484"></a><a name="p1286707219484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3559993519484"><a name="p3559993519484"></a><a name="p3559993519484"></a>备份ID。如果是备份创建的镜像，则填写为备份的ID，否则为空。</p>
    </td>
    </tr>
    <tr id="row5196396219484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p4833143119484"><a name="p4833143119484"></a><a name="p4833143119484"></a>__productcode</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2253182819484"><a name="p2253182819484"></a><a name="p2253182819484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1313876119484"><a name="p1313876119484"></a><a name="p1313876119484"></a>市场镜像的产品ID。</p>
    </td>
    </tr>
    <tr id="row5427752419484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p3440330819484"><a name="p3440330819484"></a><a name="p3440330819484"></a>__image_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p3520454019484"><a name="p3520454019484"></a><a name="p3520454019484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3299550119484"><a name="p3299550119484"></a><a name="p3299550119484"></a>镜像文件的大小，单位为字节。目前取值为大于0的字符串。</p>
    </td>
    </tr>
    <tr id="row2852405719484"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2874729419484"><a name="p2874729419484"></a><a name="p2874729419484"></a>__data_origin</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p4682946319484"><a name="p4682946319484"></a><a name="p4682946319484"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p3509015719484"><a name="p3509015719484"></a><a name="p3509015719484"></a>镜像来源。</p>
    <p id="p4737595819484"><a name="p4737595819484"></a><a name="p4737595819484"></a>公共镜像为空。</p>
    </td>
    </tr>
    <tr id="row126743427201"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1267417426203"><a name="p1267417426203"></a><a name="p1267417426203"></a>__root_origin</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p0674154212019"><a name="p0674154212019"></a><a name="p0674154212019"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p11674164212019"><a name="p11674164212019"></a><a name="p11674164212019"></a>表示当前镜像来源是从外部导入。取值：file。</p>
    </td>
    </tr>
    <tr id="row683412342439"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p197522166225"><a name="p197522166225"></a><a name="p197522166225"></a>__lazyloading</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2752101610226"><a name="p2752101610226"></a><a name="p2752101610226"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p2752191615220"><a name="p2752191615220"></a><a name="p2752191615220"></a>镜像是否支持延迟加载。取值为“True”或“False”。</p>
    </td>
    </tr>
    <tr id="row121139154315"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p74371469239"><a name="p74371469239"></a><a name="p74371469239"></a>active_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p643726112316"><a name="p643726112316"></a><a name="p643726112316"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p14438146102311"><a name="p14438146102311"></a><a name="p14438146102311"></a>镜像状态变为正常的时间。</p>
    </td>
    </tr>
    <tr id="row172123974311"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p671913384233"><a name="p671913384233"></a><a name="p671913384233"></a>__os_feature_list</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p147201038162311"><a name="p147201038162311"></a><a name="p147201038162311"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1772023842312"><a name="p1772023842312"></a><a name="p1772023842312"></a>镜像附加属性。该属性采用JSON格式来标识镜像支持的高级特性清单。</p>
    </td>
    </tr>
    <tr id="row55821842155911"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p25275315155911"><a name="p25275315155911"></a><a name="p25275315155911"></a>__sequence_num</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p5341551155911"><a name="p5341551155911"></a><a name="p5341551155911"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p30012506155911"><a name="p30012506155911"></a><a name="p30012506155911"></a>目前暂时不用</p>
    </td>
    </tr>
    <tr id="row59643047203735"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p580552184954"><a name="p580552184954"></a><a name="p580552184954"></a>__support_kvm</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p27540563184954"><a name="p27540563184954"></a><a name="p27540563184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p46304701184954"><a name="p46304701184954"></a><a name="p46304701184954"></a>如果镜像支持KVM，取值为true，否则无需增加该属性。</p>
    </td>
    </tr>
    <tr id="row3882825120219"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p23167082184954"><a name="p23167082184954"></a><a name="p23167082184954"></a>__support_xen</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p11995013184954"><a name="p11995013184954"></a><a name="p11995013184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p4154542184954"><a name="p4154542184954"></a><a name="p4154542184954"></a>如果镜像支持XEN，取值为true，否则无需增加该属性。</p>
    </td>
    </tr>
    <tr id="row58626039202222"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p39000938184954"><a name="p39000938184954"></a><a name="p39000938184954"></a>__support_largememory</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p57096932184954"><a name="p57096932184954"></a><a name="p57096932184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p651492811217"><a name="p651492811217"></a><a name="p651492811217"></a>表示该镜像支持超大内存。如果镜像支持超大内存，取值为true，否则无需增加该属性。</p>
    <p id="p463317244813"><a name="p463317244813"></a><a name="p463317244813"></a>镜像操作系统类型请参考“<a href="https://support.huaweicloud.com/productdesc-ims/ims_01_0007.html" target="_blank" rel="noopener noreferrer">弹性云服务器类型与支持的操作系统版本</a>”。</p>
    </td>
    </tr>
    <tr id="row43057536203728"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p47581434184954"><a name="p47581434184954"></a><a name="p47581434184954"></a>__support_diskintensive</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p50609959184954"><a name="p50609959184954"></a><a name="p50609959184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p20887878184954"><a name="p20887878184954"></a><a name="p20887878184954"></a>表示该镜像支持密集存储。如果镜像支持密集存储性能，则值为true，否则无需增加该属性。</p>
    </td>
    </tr>
    <tr id="row39724815224743"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p17123543184954"><a name="p17123543184954"></a><a name="p17123543184954"></a>__support_highperformance</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p38086855184954"><a name="p38086855184954"></a><a name="p38086855184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p17225863184954"><a name="p17225863184954"></a><a name="p17225863184954"></a>表示该镜像支持高计算性能。如果镜像支持高计算性能，则值为true，否则无需增加该属性。</p>
    </td>
    </tr>
    <tr id="row62323042204110"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p26024330184954"><a name="p26024330184954"></a><a name="p26024330184954"></a>__support_xen_gpu_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p15739313184954"><a name="p15739313184954"></a><a name="p15739313184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p23482902184954"><a name="p23482902184954"></a><a name="p23482902184954"></a>表示该镜像是支持XEN虚拟化平台下的GPU优化类型，取值参考<a href="相关参数取值列表.md#table65768383152758">表2</a>。如果不支持XEN虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row1584552720426"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p44343300184954"><a name="p44343300184954"></a><a name="p44343300184954"></a>__support_kvm_gpu_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p66845928184954"><a name="p66845928184954"></a><a name="p66845928184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p29779677184954"><a name="p29779677184954"></a><a name="p29779677184954"></a>表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考<a href="相关参数取值列表.md#table282523154017">表3</a>。</p>
    <p id="p44348954184954"><a name="p44348954184954"></a><a name="p44348954184954"></a>如果不支持KVM虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row16941346204313"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p7047919184954"><a name="p7047919184954"></a><a name="p7047919184954"></a>__support_xen_hana</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p47139696184954"><a name="p47139696184954"></a><a name="p47139696184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p66284528184954"><a name="p66284528184954"></a><a name="p66284528184954"></a>如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无需添加该属性。</p>
    <p id="p32685305184954"><a name="p32685305184954"></a><a name="p32685305184954"></a>该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row2879248184946"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p2966201184954"><a name="p2966201184954"></a><a name="p2966201184954"></a>__support_kvm_infiniband</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p38078563184954"><a name="p38078563184954"></a><a name="p38078563184954"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p16027374184954"><a name="p16027374184954"></a><a name="p16027374184954"></a>如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无需添加该属性。</p>
    <p id="p2859675184954"><a name="p2859675184954"></a><a name="p2859675184954"></a>该属性与“__support_xen”属性不共存。</p>
    </td>
    </tr>
    <tr id="row16212938113116"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1613123052019"><a name="p1613123052019"></a><a name="p1613123052019"></a>__support_fc_inject</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p101393072018"><a name="p101393072018"></a><a name="p101393072018"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p8706203910588"><a name="p8706203910588"></a><a name="p8706203910588"></a>表示当前镜像支持Cloud-Init密码/密钥注入方式，取值为“true”或者“false”。</p>
    <p id="p1738141097"><a name="p1738141097"></a><a name="p1738141097"></a>如果取值为“true”，表示该镜像不支持Cloud-Init注入密码/密钥，其他取值时表示支持Cloud-Init注入密钥/密码。</p>
    <div class="note" id="note18419142317116"><a name="note18419142317116"></a><a name="note18419142317116"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p164199231519"><a name="p164199231519"></a><a name="p164199231519"></a>该特性参数只对ECS系统盘镜像生效，其他类型镜像不生效。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row2944142019381"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p172919315292"><a name="p172919315292"></a><a name="p172919315292"></a>enterprise_project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p172915311293"><a name="p172915311293"></a><a name="p172915311293"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p10305182217584"><a name="p10305182217584"></a><a name="p10305182217584"></a>表示当前镜像所属的企业项目。</p>
    <a name="ul444316189359"></a><a name="ul444316189359"></a><ul id="ul444316189359"><li>取值为0或无该值，表示属于default企业项目。</li><li>取值为UUID，表示属于该UUID对应的企业项目。<p id="ims_03_0605_p178512485415"><a name="ims_03_0605_p178512485415"></a><a name="ims_03_0605_p178512485415"></a>关于企业项目ID的获取及企业项目特性的详细信息，请参考“<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业中心总览</a>”。</p>
    </li></ul>
    </td>
    </tr>
    <tr id="row157796486386"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1223217245352"><a name="p1223217245352"></a><a name="p1223217245352"></a>__is_offshelved</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p8232122410351"><a name="p8232122410351"></a><a name="p8232122410351"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p20232724133511"><a name="p20232724133511"></a><a name="p20232724133511"></a>表示当前市场镜像是否下架。</p>
    <a name="ul423215249355"></a><a name="ul423215249355"></a><ul id="ul423215249355"><li>true：已下架</li><li>false：未下架</li></ul>
    </td>
    </tr>
    <tr id="row159155884217"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p162261715424"><a name="p162261715424"></a><a name="p162261715424"></a>hw_firmware_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1522517164219"><a name="p1522517164219"></a><a name="p1522517164219"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p11221517194218"><a name="p11221517194218"></a><a name="p11221517194218"></a><span id="text98241920145218"><a name="text98241920145218"></a><a name="text98241920145218"></a></span><span id="text819992212522"><a name="text819992212522"></a><a name="text819992212522"></a>云服务器</span>的启动方式。目前支持：</p>
    <a name="ul1122141720424"></a><a name="ul1122141720424"></a><ul id="ul1122141720424"><li>bios：表示bios引导启动。</li><li>uefi：表示uefi引导启动。</li></ul>
    </td>
    </tr>
    <tr id="row585914034912"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p6742230114713"><a name="p6742230114713"></a><a name="p6742230114713"></a>hw_vif_multiqueue_enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1574213024718"><a name="p1574213024718"></a><a name="p1574213024718"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1874217309476"><a name="p1874217309476"></a><a name="p1874217309476"></a>镜像是否支持网卡多队列。取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row69153817422"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p1622217114213"><a name="p1622217114213"></a><a name="p1622217114213"></a>__support_arm</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p132251744214"><a name="p132251744214"></a><a name="p132251744214"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p112231754218"><a name="p112231754218"></a><a name="p112231754218"></a>是否为ARM架构类型的镜像。取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row14420495134"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p13420892132"><a name="p13420892132"></a><a name="p13420892132"></a>__support_agent_list</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p164204961315"><a name="p164204961315"></a><a name="p164204961315"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p74209991311"><a name="p74209991311"></a><a name="p74209991311"></a>镜像是否支持企业主机安全或主机监控。</p>
    <a name="ul2308507142"></a><a name="ul2308507142"></a><ul id="ul2308507142"><li>hss：企业主机安全</li><li>ces：主机监控</li></ul>
    <p id="p1260041621510"><a name="p1260041621510"></a><a name="p1260041621510"></a>取值样例：</p>
    <p id="p15600111615158"><a name="p15600111615158"></a><a name="p15600111615158"></a>"__support_agent_list": "hss,ces"</p>
    <div class="note" id="note16932135991718"><a name="note16932135991718"></a><a name="note16932135991718"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1493310591173"><a name="p1493310591173"></a><a name="p1493310591173"></a>如果查询结果无此字段，表示镜像不支持企业主机安全或主机监控。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row1739718404519"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p334363823112"><a name="p334363823112"></a><a name="p334363823112"></a>__account_code</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p3343133813319"><a name="p3343133813319"></a><a name="p3343133813319"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p234373810312"><a name="p234373810312"></a><a name="p234373810312"></a>收费镜像标识。</p>
    </td>
    </tr>
    <tr id="row10131151114454"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p125364213111"><a name="p125364213111"></a><a name="p125364213111"></a>__image_location</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p2253164214314"><a name="p2253164214314"></a><a name="p2253164214314"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p62531426318"><a name="p62531426318"></a><a name="p62531426318"></a>镜像的存储位置。</p>
    </td>
    </tr>
    <tr id="row18131131124519"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p425414083113"><a name="p425414083113"></a><a name="p425414083113"></a>__is_config_init</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p1254840163112"><a name="p1254840163112"></a><a name="p1254840163112"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p1825474063117"><a name="p1825474063117"></a><a name="p1825474063117"></a>是否完成了初始化配置。取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row6879183316581"><td class="cellrowborder" valign="top" width="25.27%" headers="mcps1.1.4.1.1 "><p id="p192771122195514"><a name="p192771122195514"></a><a name="p192771122195514"></a>__support_amd</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.580000000000002%" headers="mcps1.1.4.1.2 "><p id="p14278172215558"><a name="p14278172215558"></a><a name="p14278172215558"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.15%" headers="mcps1.1.4.1.3 "><p id="p227810227555"><a name="p227810227555"></a><a name="p227810227555"></a>是否是AMD架构类型的镜像。取值为“true”或者“false”。</p>
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
          "schema": "/v2/schemas/image",
          "min_disk": 100,
          "created_at": "2018-09-06T14:03:27Z",
          "__image_source_type": "uds",
          "container_format": "bare",
          "file": "/v2/images/bc6bed6e-ba3a-4447-afcc-449174a3eb52/file",
          "updated_at": "2018-09-06T15:17:33Z",
          "protected": true,
          "checksum": "d41d8cd98f00b204e9800998ecf8427e",
          "__support_kvm_fpga_type": "VU9P",
          "id": "bc6bed6e-ba3a-4447-afcc-449174a3eb52",
          "__isregistered": "true",
          "min_ram": 2048,
          "__lazyloading": "true",
          "owner": "1bed856811654c1cb661a6ca845ebc77",
          "__os_type": "Linux",
          "__imagetype": "gold",
          "visibility": "public",
          "virtual_env_type": "FusionCompute",
          "tags": [],
          "__platform": "CentOS",
          "size": 0,
          "__os_bit": "64",
          "__os_version": "CentOS 7.3 64bit",
          "name": "CentOS 7.3 64bit vivado",
          "self": "/v2/images/bc6bed6e-ba3a-4447-afcc-449174a3eb52",
          "disk_format": "zvhd2",
          "virtual_size": null,
          "status": "active"
    }
    ```


## 返回值<a name="section37356392"></a>

-   正常

    200

-   异常

    <a name="table262968317230"></a>
    <table><thead align="left"><tr id="row5740081817230"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p1895465817230"><a name="p1895465817230"></a><a name="p1895465817230"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p5893233917230"><a name="p5893233917230"></a><a name="p5893233917230"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row879015617230"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4091407017230"><a name="p4091407017230"></a><a name="p4091407017230"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2570540117230"><a name="p2570540117230"></a><a name="p2570540117230"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row176271617230"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p856227917230"><a name="p856227917230"></a><a name="p856227917230"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2245600317230"><a name="p2245600317230"></a><a name="p2245600317230"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row77743917230"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p6297256617230"><a name="p6297256617230"></a><a name="p6297256617230"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p50424217230"><a name="p50424217230"></a><a name="p50424217230"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row56011270191147"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p40619053191147"><a name="p40619053191147"></a><a name="p40619053191147"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1808959191147"><a name="p1808959191147"></a><a name="p1808959191147"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row453818617230"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3204876017230"><a name="p3204876017230"></a><a name="p3204876017230"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p4581273417230"><a name="p4581273417230"></a><a name="p4581273417230"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row966142617230"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4437803217230"><a name="p4437803217230"></a><a name="p4437803217230"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p3785084317230"><a name="p3785084317230"></a><a name="p3785084317230"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


