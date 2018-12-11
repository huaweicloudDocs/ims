# 查询镜像详情（OpenStack原生 v1.1--已废弃，不推荐使用）<a name="ZH-CN_TOPIC_0066978720"></a>

## 功能介绍<a name="section21608354152128"></a>

查询镜像列表详情。

当前接口已废弃，推荐使用[查询镜像列表（OpenStack原生）](查询镜像列表（OpenStack原生）.md)。

## URI<a name="section49016415152128"></a>

URI格式

GET /v1.1/images/detail

## 请求消息<a name="section49535636152128"></a>

-   参数说明

    可以把name，container\_format，disk\_format，status，size\_min，size\_max，changes-since作为uri参数，过滤查询结果。

    <a name="table6909858152128"></a>
    <table><thead align="left"><tr id="row2200986152128"><th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.1"><p id="p44062206152128"><a name="p44062206152128"></a><a name="p44062206152128"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p12268934152128"><a name="p12268934152128"></a><a name="p12268934152128"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p54259611152128"><a name="p54259611152128"></a><a name="p54259611152128"></a>必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.4"><p id="p32952356152128"><a name="p32952356152128"></a><a name="p32952356152128"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row51895178152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p42759860152128"><a name="p42759860152128"></a><a name="p42759860152128"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p40996618152128"><a name="p40996618152128"></a><a name="p40996618152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p32391798152128"><a name="p32391798152128"></a><a name="p32391798152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p6489949152128"><a name="p6489949152128"></a><a name="p6489949152128"></a>镜像名称。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row58409547152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p33552889152128"><a name="p33552889152128"></a><a name="p33552889152128"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p33429463152128"><a name="p33429463152128"></a><a name="p33429463152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p23431949152128"><a name="p23431949152128"></a><a name="p23431949152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p18939716152128"><a name="p18939716152128"></a><a name="p18939716152128"></a>镜像容器类型</p>
    </td>
    </tr>
    <tr id="row36239719152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p49736130152128"><a name="p49736130152128"></a><a name="p49736130152128"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p2094705152128"><a name="p2094705152128"></a><a name="p2094705152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p35453405152128"><a name="p35453405152128"></a><a name="p35453405152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p53153517152128"><a name="p53153517152128"></a><a name="p53153517152128"></a>镜像文件格式</p>
    </td>
    </tr>
    <tr id="row8619606152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p27099480152128"><a name="p27099480152128"></a><a name="p27099480152128"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p47574258152128"><a name="p47574258152128"></a><a name="p47574258152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p28309709152128"><a name="p28309709152128"></a><a name="p28309709152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p11385105152128"><a name="p11385105152128"></a><a name="p11385105152128"></a>镜像状态</p>
    </td>
    </tr>
    <tr id="row35357081152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p45351308152128"><a name="p45351308152128"></a><a name="p45351308152128"></a>size_min</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p49577340152128"><a name="p49577340152128"></a><a name="p49577340152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p56341584152128"><a name="p56341584152128"></a><a name="p56341584152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p265585152128"><a name="p265585152128"></a><a name="p265585152128"></a>镜像不小于</p>
    </td>
    </tr>
    <tr id="row2390265152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p59393783152128"><a name="p59393783152128"></a><a name="p59393783152128"></a>size_max</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p46167158152128"><a name="p46167158152128"></a><a name="p46167158152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p48552350152128"><a name="p48552350152128"></a><a name="p48552350152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p40426262152128"><a name="p40426262152128"></a><a name="p40426262152128"></a>镜像不大于</p>
    </td>
    </tr>
    <tr id="row28292039152128"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p9953851152128"><a name="p9953851152128"></a><a name="p9953851152128"></a>changes-since</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p955603152128"><a name="p955603152128"></a><a name="p955603152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p10295032152128"><a name="p10295032152128"></a><a name="p10295032152128"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><p id="p28591249152128"><a name="p28591249152128"></a><a name="p28591249152128"></a>镜像最后更新时间</p>
    </td>
    </tr>
    </tbody>
    </table>

-   请求样例

    ```
    GET /v1.1/images/detail?disk_format=qcow2
    ```


## 响应<a name="section55994653152128"></a>

-   参数说明

    <a name="table39273024152128"></a>
    <table><thead align="left"><tr id="row54360090152128"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p41091190152128"><a name="p41091190152128"></a><a name="p41091190152128"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p40052127152128"><a name="p40052127152128"></a><a name="p40052127152128"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p50806390152128"><a name="p50806390152128"></a><a name="p50806390152128"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row21676916152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p10999775152128"><a name="p10999775152128"></a><a name="p10999775152128"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p18566558152128"><a name="p18566558152128"></a><a name="p18566558152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p12601146152128"><a name="p12601146152128"></a><a name="p12601146152128"></a>镜像状态</p>
    </td>
    </tr>
    <tr id="row46301451152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p59430045152128"><a name="p59430045152128"></a><a name="p59430045152128"></a>virtual_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p49104327152128"><a name="p49104327152128"></a><a name="p49104327152128"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p50947078152128"><a name="p50947078152128"></a><a name="p50947078152128"></a>镜像虚拟大小</p>
    </td>
    </tr>
    <tr id="row55870518152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p29218105152128"><a name="p29218105152128"></a><a name="p29218105152128"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p17856313152128"><a name="p17856313152128"></a><a name="p17856313152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p50303566152128"><a name="p50303566152128"></a><a name="p50303566152128"></a>镜像名称。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row50078910152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p29859916152128"><a name="p29859916152128"></a><a name="p29859916152128"></a>deleted</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p2734171152128"><a name="p2734171152128"></a><a name="p2734171152128"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p20835099152128"><a name="p20835099152128"></a><a name="p20835099152128"></a>镜像是否已删除</p>
    </td>
    </tr>
    <tr id="row53298164152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p22184056152128"><a name="p22184056152128"></a><a name="p22184056152128"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p52078112152128"><a name="p52078112152128"></a><a name="p52078112152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p33270526152128"><a name="p33270526152128"></a><a name="p33270526152128"></a>镜像容器类型</p>
    </td>
    </tr>
    <tr id="row30999282152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p27913893152128"><a name="p27913893152128"></a><a name="p27913893152128"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p46432832152128"><a name="p46432832152128"></a><a name="p46432832152128"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p38680656152128"><a name="p38680656152128"></a><a name="p38680656152128"></a>镜像创建时间</p>
    </td>
    </tr>
    <tr id="row12581591152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p12475971152128"><a name="p12475971152128"></a><a name="p12475971152128"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p3920764152128"><a name="p3920764152128"></a><a name="p3920764152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p21441395152128"><a name="p21441395152128"></a><a name="p21441395152128"></a>镜像文件类型</p>
    </td>
    </tr>
    <tr id="row58754830152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p61520781152128"><a name="p61520781152128"></a><a name="p61520781152128"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p17127389152128"><a name="p17127389152128"></a><a name="p17127389152128"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p32565519152128"><a name="p32565519152128"></a><a name="p32565519152128"></a>镜像更新时间</p>
    </td>
    </tr>
    <tr id="row24654215152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p50834371152128"><a name="p50834371152128"></a><a name="p50834371152128"></a>properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p23943412152128"><a name="p23943412152128"></a><a name="p23943412152128"></a>Dict</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p57990740152128"><a name="p57990740152128"></a><a name="p57990740152128"></a>镜像属性</p>
    </td>
    </tr>
    <tr id="row52154619152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p63774574152128"><a name="p63774574152128"></a><a name="p63774574152128"></a>owner</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65466907152128"><a name="p65466907152128"></a><a name="p65466907152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p31649597152128"><a name="p31649597152128"></a><a name="p31649597152128"></a>镜像所属租户</p>
    </td>
    </tr>
    <tr id="row16410923152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p54216352152128"><a name="p54216352152128"></a><a name="p54216352152128"></a>protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p29448369152128"><a name="p29448369152128"></a><a name="p29448369152128"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p4335306152128"><a name="p4335306152128"></a><a name="p4335306152128"></a>镜像是否受保护</p>
    </td>
    </tr>
    <tr id="row39017760152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p6321968152128"><a name="p6321968152128"></a><a name="p6321968152128"></a>min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p42317409152128"><a name="p42317409152128"></a><a name="p42317409152128"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p15153476152128"><a name="p15153476152128"></a><a name="p15153476152128"></a>运行镜像所需最小内存，单位MB</p>
    </td>
    </tr>
    <tr id="row2163563152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p41030913152128"><a name="p41030913152128"></a><a name="p41030913152128"></a>checksum</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p35169627152128"><a name="p35169627152128"></a><a name="p35169627152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p27650173152128"><a name="p27650173152128"></a><a name="p27650173152128"></a>镜像校验和，上传镜像文件后存在</p>
    </td>
    </tr>
    <tr id="row47524965152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p24316986152128"><a name="p24316986152128"></a><a name="p24316986152128"></a>min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p23518872152128"><a name="p23518872152128"></a><a name="p23518872152128"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p24041996152128"><a name="p24041996152128"></a><a name="p24041996152128"></a>运行镜像所需最小磁盘，单位GB</p>
    </td>
    </tr>
    <tr id="row15051376152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p11201934152128"><a name="p11201934152128"></a><a name="p11201934152128"></a>is_public</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p34941465152128"><a name="p34941465152128"></a><a name="p34941465152128"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p7073684152128"><a name="p7073684152128"></a><a name="p7073684152128"></a>是否为公共镜像</p>
    </td>
    </tr>
    <tr id="row63663156152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p56441973152128"><a name="p56441973152128"></a><a name="p56441973152128"></a>deleted_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p8397095152128"><a name="p8397095152128"></a><a name="p8397095152128"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p64073980152128"><a name="p64073980152128"></a><a name="p64073980152128"></a>镜像删除时间</p>
    </td>
    </tr>
    <tr id="row39794913152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2162544152128"><a name="p2162544152128"></a><a name="p2162544152128"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p40948371152128"><a name="p40948371152128"></a><a name="p40948371152128"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p25483447152128"><a name="p25483447152128"></a><a name="p25483447152128"></a>镜像UUID</p>
    </td>
    </tr>
    <tr id="row28024434152128"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p55386696152128"><a name="p55386696152128"></a><a name="p55386696152128"></a>size</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p57137398152128"><a name="p57137398152128"></a><a name="p57137398152128"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p8360445152128"><a name="p8360445152128"></a><a name="p8360445152128"></a>镜像大小，上传镜像文件后存在</p>
    </td>
    </tr>
    </tbody>
    </table>

-   响应样例

    ```
    HTTP/1.1 200 OK
    ```

    ```
    Content-Type: application/json; charset=UTF-8
    Content-Length: 495
    X-Openstack-Request-Id: req-68327dda-8078-41fe-b091-01a09ec073da
    Date: Mon, 23 May 2016 02:32:28 GMT
    
    {
    "images": [
    {
    "status": "active",
    "deleted_at": none,
    "name": "cirros",
    "deleted": false,
    "container_format": "bare",
    "created_at": "2016-05-22T06:04:20.425843",
    "disk_format": "qcow2",
    "updated_at": "2016-05-22T06:04:22.719791",
    "min_disk": 0,
    "protected": false,
    "id": "3c3d1d01-b48a-4639-8a88-08be3b9b5d78",
    "min_ram": 0,
    "checksum": "64d7c1cd2b6f60c92c14662941cb7913",
    "owner": "23f4cb75768d4febb39542ef6fe169f3",
    "is_public": true,
    "virtual_size": null,
    "properties": {},
    "size": 13167616
    }
    ]
    }
    ```


## 错误码<a name="section61208656152128"></a>

不涉及。

