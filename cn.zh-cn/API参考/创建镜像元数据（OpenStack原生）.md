# 创建镜像元数据（OpenStack原生）<a name="ZH-CN_TOPIC_0031615565"></a>

## 功能介绍<a name="section66302617144828"></a>

创建镜像元数据。

调用创建镜像元数据接口成功后，只是创建了镜像的元数据，镜像对应的实际镜像文件并不存在。

## URI<a name="section16226363144828"></a>

POST /v2/images

## 请求消息<a name="section22707920144828"></a>

-   请求参数

    <a name="table53011268153646"></a>
    <table><thead align="left"><tr id="row8255548153646"><th class="cellrowborder" valign="top" width="20.18%" id="mcps1.1.5.1.1"><p id="p64719651153646"><a name="p64719651153646"></a><a name="p64719651153646"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.12%" id="mcps1.1.5.1.2"><p id="p7800370153646"><a name="p7800370153646"></a><a name="p7800370153646"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.29%" id="mcps1.1.5.1.3"><p id="p27850258153646"><a name="p27850258153646"></a><a name="p27850258153646"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="41.410000000000004%" id="mcps1.1.5.1.4"><p id="p41278443153646"><a name="p41278443153646"></a><a name="p41278443153646"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row55219556153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p43599013153646"><a name="p43599013153646"></a><a name="p43599013153646"></a>__os_version</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p41859159153646"><a name="p41859159153646"></a><a name="p41859159153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p35148705153646"><a name="p35148705153646"></a><a name="p35148705153646"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p28472876153646"><a name="p28472876153646"></a><a name="p28472876153646"></a>镜像的操作系统具体版本，取值范围见<a href="相关参数取值列表.md">相关参数取值列表</a>。</p>
    <p id="p24601632153646"><a name="p24601632153646"></a><a name="p24601632153646"></a>如果未指定__os_version，则默认设置为Other Linux(64 bit)，不保证该镜像能成功创建虚拟机以及通过该镜像创建的虚拟机能够正常使用。</p>
    </td>
    </tr>
    <tr id="row20088096153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p16523075153646"><a name="p16523075153646"></a><a name="p16523075153646"></a>visibility</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p63300707153646"><a name="p63300707153646"></a><a name="p63300707153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p27083623153646"><a name="p27083623153646"></a><a name="p27083623153646"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p46289848153646"><a name="p46289848153646"></a><a name="p46289848153646"></a>其他租户是否可见。</p>
    <p id="p13955448153646"><a name="p13955448153646"></a><a name="p13955448153646"></a>默认取值为private。创建镜像元数据时，visibility取值只能为private。</p>
    </td>
    </tr>
    <tr id="row56649510153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p25207637153646"><a name="p25207637153646"></a><a name="p25207637153646"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p28552749153646"><a name="p28552749153646"></a><a name="p28552749153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p31071317153646"><a name="p31071317153646"></a><a name="p31071317153646"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p33748725153646"><a name="p33748725153646"></a><a name="p33748725153646"></a>镜像名称，如果未指定name的取值，则默认为空，但是使用该镜像创建虚拟机会失败。名称的长度为1～255位。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。默认值为空。</p>
    </td>
    </tr>
    <tr id="row49292214153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p33246399153646"><a name="p33246399153646"></a><a name="p33246399153646"></a>protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p8603833153646"><a name="p8603833153646"></a><a name="p8603833153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p25821900153646"><a name="p25821900153646"></a><a name="p25821900153646"></a>Boolean</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p11199135153646"><a name="p11199135153646"></a><a name="p11199135153646"></a>镜像是否被保护，保护后的镜像不可删除。默认取值为false。</p>
    </td>
    </tr>
    <tr id="row34714714153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p6985178153646"><a name="p6985178153646"></a><a name="p6985178153646"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p28928513153646"><a name="p28928513153646"></a><a name="p28928513153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p61508237153646"><a name="p61508237153646"></a><a name="p61508237153646"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p16111334153646"><a name="p16111334153646"></a><a name="p16111334153646"></a>容器格式。</p>
    <p id="p10784283153646"><a name="p10784283153646"></a><a name="p10784283153646"></a>默认取值为bare。</p>
    </td>
    </tr>
    <tr id="row29949683153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p10005277153646"><a name="p10005277153646"></a><a name="p10005277153646"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p5121099153646"><a name="p5121099153646"></a><a name="p5121099153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p12155878153646"><a name="p12155878153646"></a><a name="p12155878153646"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p45102037153646"><a name="p45102037153646"></a><a name="p45102037153646"></a>镜像文件格式。目前支持vhd、zvhd、zvhd2、raw、qcow2。默认取值为vhd。</p>
    </td>
    </tr>
    <tr id="row29386369153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p31485649153646"><a name="p31485649153646"></a><a name="p31485649153646"></a>tags</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p200749153646"><a name="p200749153646"></a><a name="p200749153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p16260734153646"><a name="p16260734153646"></a><a name="p16260734153646"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p42051116153646"><a name="p42051116153646"></a><a name="p42051116153646"></a>镜像标签列表。长度为1～255位。默认为空。</p>
    </td>
    </tr>
    <tr id="row50697246153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p12836285153646"><a name="p12836285153646"></a><a name="p12836285153646"></a>min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p33106160153646"><a name="p33106160153646"></a><a name="p33106160153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p64353312153646"><a name="p64353312153646"></a><a name="p64353312153646"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p45235764153646"><a name="p45235764153646"></a><a name="p45235764153646"></a>镜像运行需要的最小内存，单位为MB。参数取值依据<span id="text826912402084"><a name="text826912402084"></a><a name="text826912402084"></a></span><span id="text1496184118812"><a name="text1496184118812"></a><a name="text1496184118812"></a>云服务器</span>的规格限制。默认取值为0。</p>
    <p id="p574912347473"><a name="p574912347473"></a><a name="p574912347473"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
    </td>
    </tr>
    <tr id="row4468695153646"><td class="cellrowborder" valign="top" width="20.18%" headers="mcps1.1.5.1.1 "><p id="p26420029153646"><a name="p26420029153646"></a><a name="p26420029153646"></a>min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.12%" headers="mcps1.1.5.1.2 "><p id="p59647611153646"><a name="p59647611153646"></a><a name="p59647611153646"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.29%" headers="mcps1.1.5.1.3 "><p id="p66727226153646"><a name="p66727226153646"></a><a name="p66727226153646"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="41.410000000000004%" headers="mcps1.1.5.1.4 "><p id="p38417884203334"><a name="p38417884203334"></a><a name="p38417884203334"></a>镜像运行需要的最小磁盘，单位为GB 。取值为40～1024GB。</p>
    <p id="p57330868153646"><a name="p57330868153646"></a><a name="p57330868153646"></a>必须大于镜像系统盘容量，否则创建<span id="text1126650384"><a name="text1126650384"></a><a name="text1126650384"></a></span><span id="text182617501488"><a name="text182617501488"></a><a name="text182617501488"></a>云服务器</span>可能失败。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >可以在请求样例的body体中增加key:value的字段，key字符串长度不超过255，value可以为空字符串。  


-   请求样例

    ```
    POST https://{Endpoint}/v2/images
    ```

    ```
    {
        "__os_version": "Ubuntu 14.04 server 64bit",
        "container_format": "bare",
        "disk_format": "vhd",
        "min_disk": 1,
        "min_ram": 1024,
        "name": "test",
        "tags": [
            "test",
            "image"
        ],
        "visibility": "private",
        "protected": false,
        "aaaa":"11111"
    }
    ```


## 响应消息<a name="section37386190144828"></a>

-   响应参数

    <a name="table65680948153746"></a>
    <table><thead align="left"><tr id="row59664825153746"><th class="cellrowborder" valign="top" width="27.229999999999997%" id="mcps1.1.4.1.1"><p id="p1012670153746"><a name="p1012670153746"></a><a name="p1012670153746"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="24.54%" id="mcps1.1.4.1.2"><p id="p352397153746"><a name="p352397153746"></a><a name="p352397153746"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="48.230000000000004%" id="mcps1.1.4.1.3"><p id="p28544167153746"><a name="p28544167153746"></a><a name="p28544167153746"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row30376173153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p44550985153746"><a name="p44550985153746"></a><a name="p44550985153746"></a>visibility</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p39910492153746"><a name="p39910492153746"></a><a name="p39910492153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p11524453153746"><a name="p11524453153746"></a><a name="p11524453153746"></a>其他租户是否可见。取值为private。</p>
    </td>
    </tr>
    <tr id="row61065506153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p47358972153746"><a name="p47358972153746"></a><a name="p47358972153746"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p8177445153746"><a name="p8177445153746"></a><a name="p8177445153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p58393284153746"><a name="p58393284153746"></a><a name="p58393284153746"></a>镜像名称，如果未指定name的取值，则默认为空，但是使用该镜像创建虚拟机会失败。名称的长度为1～128位。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row32235552153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p60942880153746"><a name="p60942880153746"></a><a name="p60942880153746"></a>protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p11625005153746"><a name="p11625005153746"></a><a name="p11625005153746"></a>Boolean</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p2101387153746"><a name="p2101387153746"></a><a name="p2101387153746"></a>镜像是否被保护，保护后的镜像不可删除。取值为false。</p>
    </td>
    </tr>
    <tr id="row35994669153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p29887100153746"><a name="p29887100153746"></a><a name="p29887100153746"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p64274239153746"><a name="p64274239153746"></a><a name="p64274239153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p3986378091022"><a name="p3986378091022"></a><a name="p3986378091022"></a>容器格式。</p>
    <p id="p2322970491022"><a name="p2322970491022"></a><a name="p2322970491022"></a>取值为bare。</p>
    </td>
    </tr>
    <tr id="row58291220153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p23968345153746"><a name="p23968345153746"></a><a name="p23968345153746"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p20244641153746"><a name="p20244641153746"></a><a name="p20244641153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p2302086591022"><a name="p2302086591022"></a><a name="p2302086591022"></a>镜像文件格式。目前支持vhd、zvhd、raw、qcow2。默认值是vhd。</p>
    </td>
    </tr>
    <tr id="row16647962153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p6307710153746"><a name="p6307710153746"></a><a name="p6307710153746"></a>tags</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p45828379153746"><a name="p45828379153746"></a><a name="p45828379153746"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p21111204153746"><a name="p21111204153746"></a><a name="p21111204153746"></a>镜像标签列表。长度为1～255位。</p>
    </td>
    </tr>
    <tr id="row32285962153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p65026100153746"><a name="p65026100153746"></a><a name="p65026100153746"></a>min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p25195510153746"><a name="p25195510153746"></a><a name="p25195510153746"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p27570397153746"><a name="p27570397153746"></a><a name="p27570397153746"></a>镜像运行最小内存，单位为MB。取值参考ECS规格限制，一般设置为0。</p>
    <p id="p19726102415119"><a name="p19726102415119"></a><a name="p19726102415119"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
    </td>
    </tr>
    <tr id="row46806987153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p33269625153746"><a name="p33269625153746"></a><a name="p33269625153746"></a>min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p43985037153746"><a name="p43985037153746"></a><a name="p43985037153746"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p33012089153426"><a name="p33012089153426"></a><a name="p33012089153426"></a>镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。必须大于镜像系统盘容量，否则创建<span id="text1810514495915"><a name="text1810514495915"></a><a name="text1810514495915"></a></span><span id="text186857585917"><a name="text186857585917"></a><a name="text186857585917"></a>云服务器</span>可能失败。</p>
    </td>
    </tr>
    <tr id="row17715747153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p25689427153746"><a name="p25689427153746"></a><a name="p25689427153746"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p127882921768"><a name="p127882921768"></a><a name="p127882921768"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p29539523155411"><a name="p29539523155411"></a><a name="p29539523155411"></a>镜像状态。取值如下：</p>
    <a name="ul64671162155411"></a><a name="ul64671162155411"></a><ul id="ul64671162155411"><li>queued：表示镜像元数据已经创建成功，等待上传镜像文件。</li><li>saving：表示镜像正在上传文件到后端存储。</li><li>deleted：表示镜像已经删除。</li><li>killed：表示镜像上传错误。</li><li>active：表示镜像可以正常使用。</li></ul>
    </td>
    </tr>
    <tr id="row36868745153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p33578394153746"><a name="p33578394153746"></a><a name="p33578394153746"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p56557754153746"><a name="p56557754153746"></a><a name="p56557754153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p17775385153746"><a name="p17775385153746"></a><a name="p17775385153746"></a>创建时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row25760740153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p6245233153746"><a name="p6245233153746"></a><a name="p6245233153746"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p38569043153746"><a name="p38569043153746"></a><a name="p38569043153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p37084793153746"><a name="p37084793153746"></a><a name="p37084793153746"></a>更新时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row65327686153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p57051191153746"><a name="p57051191153746"></a><a name="p57051191153746"></a>self</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p46735376153746"><a name="p46735376153746"></a><a name="p46735376153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p27469127153746"><a name="p27469127153746"></a><a name="p27469127153746"></a>本镜像链接。</p>
    </td>
    </tr>
    <tr id="row45895558153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p26552727153746"><a name="p26552727153746"></a><a name="p26552727153746"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p64943162153746"><a name="p64943162153746"></a><a name="p64943162153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p25904797153746"><a name="p25904797153746"></a><a name="p25904797153746"></a>镜像ID，用户调用创建镜像接口后，需保存该镜像的ID，用来调用上传镜像接口完成镜像上传。</p>
    </td>
    </tr>
    <tr id="row31816583153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p27006401153746"><a name="p27006401153746"></a><a name="p27006401153746"></a>file</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p21597859153746"><a name="p21597859153746"></a><a name="p21597859153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p4596122153746"><a name="p4596122153746"></a><a name="p4596122153746"></a>上传下载镜像文件的地址链接。</p>
    </td>
    </tr>
    <tr id="row41365104153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p62239150153746"><a name="p62239150153746"></a><a name="p62239150153746"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p60735714153746"><a name="p60735714153746"></a><a name="p60735714153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p20645801153746"><a name="p20645801153746"></a><a name="p20645801153746"></a>视图链接。</p>
    </td>
    </tr>
    <tr id="row51594484153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p18403679153746"><a name="p18403679153746"></a><a name="p18403679153746"></a>__image_source_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p17692826153746"><a name="p17692826153746"></a><a name="p17692826153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p23832762153746"><a name="p23832762153746"></a><a name="p23832762153746"></a>镜像后端存储类型，目前支持uds。</p>
    </td>
    </tr>
    <tr id="row13168267153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p59996701153746"><a name="p59996701153746"></a><a name="p59996701153746"></a>__image_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p44870066153746"><a name="p44870066153746"></a><a name="p44870066153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p10596742153746"><a name="p10596742153746"></a><a name="p10596742153746"></a>镜像大小。单位为字节。</p>
    </td>
    </tr>
    <tr id="row28261814153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p7505593153746"><a name="p7505593153746"></a><a name="p7505593153746"></a>__isregistered</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p53402269153746"><a name="p53402269153746"></a><a name="p53402269153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p30616526153746"><a name="p30616526153746"></a><a name="p30616526153746"></a>镜像是否注册。只有已注册的镜像才能在Portal界面上查询到。取值为true。</p>
    </td>
    </tr>
    <tr id="row64019507153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p18197556153746"><a name="p18197556153746"></a><a name="p18197556153746"></a>__os_version</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p7501613153746"><a name="p7501613153746"></a><a name="p7501613153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p3650932153746"><a name="p3650932153746"></a><a name="p3650932153746"></a>镜像的操作系统具体版本，取值范围见<a href="相关参数取值列表.md">相关参数取值列表</a>。</p>
    </td>
    </tr>
    <tr id="row27290104153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p63014816153746"><a name="p63014816153746"></a><a name="p63014816153746"></a>__os_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p49609854153746"><a name="p49609854153746"></a><a name="p49609854153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p58975236153746"><a name="p58975236153746"></a><a name="p58975236153746"></a>镜像的操作系统类型，取值由__os_version确定。支持Windows、Linux和other。</p>
    </td>
    </tr>
    <tr id="row61015077153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p43274176153746"><a name="p43274176153746"></a><a name="p43274176153746"></a>__platform</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p51377616153746"><a name="p51377616153746"></a><a name="p51377616153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p837397153746"><a name="p837397153746"></a><a name="p837397153746"></a>表示镜像支持的操作系统平台。取值由__os_version确定</p>
    </td>
    </tr>
    <tr id="row7536579153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p6483196153746"><a name="p6483196153746"></a><a name="p6483196153746"></a>__os_bit</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p56341747153746"><a name="p56341747153746"></a><a name="p56341747153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p278785153746"><a name="p278785153746"></a><a name="p278785153746"></a>表示操作系统位数。取值由__os_version确定，取值为32或64。</p>
    </td>
    </tr>
    <tr id="row2509069153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p1908061153746"><a name="p1908061153746"></a><a name="p1908061153746"></a>__imagetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p36544143153746"><a name="p36544143153746"></a><a name="p36544143153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p7285568153746"><a name="p7285568153746"></a><a name="p7285568153746"></a>镜像类型。取值为private，表示私有镜像。</p>
    </td>
    </tr>
    <tr id="row34742228153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p62657107153746"><a name="p62657107153746"></a><a name="p62657107153746"></a>virtual_env_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p51489910153746"><a name="p51489910153746"></a><a name="p51489910153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p9933162153746"><a name="p9933162153746"></a><a name="p9933162153746"></a>平台类型。</p>
    <p id="p1364519165504"><a name="p1364519165504"></a><a name="p1364519165504"></a>镜像使用环境类型：FusionCompute、Ironic、DataImage。</p>
    <a name="ul1113018265506"></a><a name="ul1113018265506"></a><ul id="ul1113018265506"><li>如果是<span id="text8147214578"><a name="text8147214578"></a><a name="text8147214578"></a></span><span id="text265842125715"><a name="text265842125715"></a><a name="text265842125715"></a>云服务器</span>镜像，则取值为FusionCompute。</li><li>如果是数据卷镜像，则取值为DataImage。</li><li>如果是<span id="text879812283570"><a name="text879812283570"></a><a name="text879812283570"></a></span><span id="text1135718303573"><a name="text1135718303573"></a><a name="text1135718303573"></a>裸金属服务器</span>镜像，则取值为Ironic。</li></ul>
    </td>
    </tr>
    <tr id="row66388651153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p8771616153746"><a name="p8771616153746"></a><a name="p8771616153746"></a>owner</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p38277576153746"><a name="p38277576153746"></a><a name="p38277576153746"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p13475914153746"><a name="p13475914153746"></a><a name="p13475914153746"></a>镜像所属项目ID。</p>
    </td>
    </tr>
    <tr id="row54174368153746"><td class="cellrowborder" valign="top" width="27.229999999999997%" headers="mcps1.1.4.1.1 "><p id="p26047664153746"><a name="p26047664153746"></a><a name="p26047664153746"></a>virtual_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.54%" headers="mcps1.1.4.1.2 "><p id="p39559770153746"><a name="p39559770153746"></a><a name="p39559770153746"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.230000000000004%" headers="mcps1.1.4.1.3 "><p id="p50224836153746"><a name="p50224836153746"></a><a name="p50224836153746"></a>镜像虚拟大小。单位为字节。</p>
    </td>
    </tr>
    </tbody>
    </table>


-   响应样例

    ```
    STATUS CODE 201
    ```

    ```
    {
        "schema": "/v2/schemas/image",
        "min_disk": 1,
        "created_at": "2016-06-02T07:49:48Z",
        "__image_source_type": "uds",
        "container_format": "bare",
        "__image_size": "0",
        "file": "/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86/file",
        "updated_at": "2016-06-02T07:49:49Z",
        "protected": false,
        "id": "4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86",
        "__isregistered": "true",
        "min_ram": 1024,
        "owner": "b912fb4a4c464b568ecfca1071b21b10",
        "__os_type": "Linux",
        "__imagetype": "private",
        "visibility": "private",
        "virtual_env_type": "FusionCompute",
        "tags": [
            "test",
            "image"
        ],
        "__platform": "Ubuntu",
        "__os_bit": "64",
        "__os_version": "Ubuntu 14.04 server 64bit",
        "name": "test",
        "self": "/v2/images/4ca46bf1-5c61-48ff-b4f3-0ad4e5e3ba86",
        "disk_format": "vhd",
        "status": "queued"
    }
    ```


## 返回值<a name="section55843593"></a>

-   正常

    201

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


