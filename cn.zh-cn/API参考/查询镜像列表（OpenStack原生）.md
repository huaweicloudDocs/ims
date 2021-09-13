# 查询镜像列表（OpenStack原生）<a name="ims_03_0702"></a>

## 功能介绍<a name="section59471393"></a>

获取镜像列表。

使用本接口查询镜像列表时，需要使用分页查询才能返回全部的镜像列表。

## 分页说明<a name="section165587269201"></a>

分页是指返回一组镜像的一个子集，在返回的时候会存在下个子集的链接和首个子集的链接，默认返回的子集中数量为25，用户也可以通过使用limit和marker两个参数自己分页，指定返回子集中需要返回的数量。

响应中的参数first是查询首页的URL。next是查询下一页的URL。当查询镜像列表最后一页时，不存在next。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceListImages)中调试该接口。

## URI<a name="section65480490"></a>

GET /v2/images

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   可以在URI后面用‘?’和‘&’添加不同的查询条件组合，请参考请求样例。
>-   如需使用OpenStack Queens版本API，请在请求消息头中包含X-Api-Version。当X-Api-Version取值大于M则返回Queens版本的结果，小于等于M，返回Mitaka版本结果 。

参数说明请参见[表1](#table33420935171457)。

**表 1**  参数说明

<a name="table33420935171457"></a>
<table><thead align="left"><tr id="row56943395171457"><th class="cellrowborder" valign="top" width="19.16191619161916%" id="mcps1.2.5.1.1"><p id="p2577832171521"><a name="p2577832171521"></a><a name="p2577832171521"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="17.241724172417243%" id="mcps1.2.5.1.2"><p id="p7477841171521"><a name="p7477841171521"></a><a name="p7477841171521"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.4018401840184%" id="mcps1.2.5.1.3"><p id="p3754553172418"><a name="p3754553172418"></a><a name="p3754553172418"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="45.1945194519452%" id="mcps1.2.5.1.4"><p id="p57397527172421"><a name="p57397527172421"></a><a name="p57397527172421"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row7130167171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p31986361171514"><a name="p31986361171514"></a><a name="p31986361171514"></a>__isregistered</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p40758410171514"><a name="p40758410171514"></a><a name="p40758410171514"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p43890043172418"><a name="p43890043172418"></a><a name="p43890043172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p37340191172421"><a name="p37340191172421"></a><a name="p37340191172421"></a>镜像是否可用，取值为true，扩展接口会默认为true，普通用户只能查询取值为true的镜像。</p>
</td>
</tr>
<tr id="row4824363171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p18187484171514"><a name="p18187484171514"></a><a name="p18187484171514"></a>__imagetype</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p63900110171514"><a name="p63900110171514"></a><a name="p63900110171514"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p64847277172418"><a name="p64847277172418"></a><a name="p64847277172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p10541175163112"><a name="p10541175163112"></a><a name="p10541175163112"></a>镜像类型，目前支持以下类型：</p>
<a name="ul45412511314"></a><a name="ul45412511314"></a><ul id="ul45412511314"><li>公共镜像：gold</li><li>私有镜像：private</li><li>共享镜像：shared</li></ul>
</td>
</tr>
<tr id="row53979171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p41763237171514"><a name="p41763237171514"></a><a name="p41763237171514"></a>protected</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p27379026171514"><a name="p27379026171514"></a><a name="p27379026171514"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p32804702172418"><a name="p32804702172418"></a><a name="p32804702172418"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p17378076172421"><a name="p17378076172421"></a><a name="p17378076172421"></a>镜像是否是受保护，取值为true/false。一般查询公共镜像时候取值为true，查询私有镜像可以不指定。</p>
</td>
</tr>
<tr id="row64237648171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p51588314171514"><a name="p51588314171514"></a><a name="p51588314171514"></a>visibility</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p17903883171514"><a name="p17903883171514"></a><a name="p17903883171514"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p263785172418"><a name="p263785172418"></a><a name="p263785172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p14732836101910"><a name="p14732836101910"></a><a name="p14732836101910"></a>是否被其他租户可见，取值如下：</p>
<a name="ul1056613910205"></a><a name="ul1056613910205"></a><ul id="ul1056613910205"><li>public：公共镜像</li><li>private：私有镜像</li><li>shared：共享镜像</li></ul>
</td>
</tr>
<tr id="row46885915171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p40504458171514"><a name="p40504458171514"></a><a name="p40504458171514"></a>owner</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p59635642171514"><a name="p59635642171514"></a><a name="p59635642171514"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p25988654172418"><a name="p25988654172418"></a><a name="p25988654172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p34708322172421"><a name="p34708322172421"></a><a name="p34708322172421"></a>镜像属于哪个租户。</p>
</td>
</tr>
<tr id="row42514069171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p45188792171710"><a name="p45188792171710"></a><a name="p45188792171710"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p36413517171710"><a name="p36413517171710"></a><a name="p36413517171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p65237974172418"><a name="p65237974172418"></a><a name="p65237974172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p2325353172421"><a name="p2325353172421"></a><a name="p2325353172421"></a>镜像ID。</p>
</td>
</tr>
<tr id="row44909088171457"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p13802561171710"><a name="p13802561171710"></a><a name="p13802561171710"></a>status</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p44265688171710"><a name="p44265688171710"></a><a name="p44265688171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p22641299172418"><a name="p22641299172418"></a><a name="p22641299172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p32131061155224"><a name="p32131061155224"></a><a name="p32131061155224"></a>镜像状态。取值如下：</p>
<a name="ul43292299155227"></a><a name="ul43292299155227"></a><ul id="ul43292299155227"><li>queued：表示镜像元数据已经创建成功，等待上传镜像文件。</li><li>saving：表示镜像正在上传文件到后端存储。</li><li>deleted：表示镜像已经删除。</li><li>killed：表示镜像上传错误。</li><li>active：表示镜像可以正常使用。</li></ul>
</td>
</tr>
<tr id="row44646789171639"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p21468736171710"><a name="p21468736171710"></a><a name="p21468736171710"></a>name</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p61246065171710"><a name="p61246065171710"></a><a name="p61246065171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p7274972172418"><a name="p7274972172418"></a><a name="p7274972172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p25100359152023"><a name="p25100359152023"></a><a name="p25100359152023"></a>镜像名称，匹配规则为精确匹配。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
</td>
</tr>
<tr id="row29378995171639"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p22241787171710"><a name="p22241787171710"></a><a name="p22241787171710"></a>container_format</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p56754321171710"><a name="p56754321171710"></a><a name="p56754321171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p31034804172418"><a name="p31034804172418"></a><a name="p31034804172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p62817831172421"><a name="p62817831172421"></a><a name="p62817831172421"></a>容器类型。默认值是bare。</p>
</td>
</tr>
<tr id="row41290451171646"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p3457793171710"><a name="p3457793171710"></a><a name="p3457793171710"></a>disk_format</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p11645813171710"><a name="p11645813171710"></a><a name="p11645813171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p19611874172418"><a name="p19611874172418"></a><a name="p19611874172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p25954213172421"><a name="p25954213172421"></a><a name="p25954213172421"></a>镜像格式，目前支持vhd、zvhd、raw、qcow2。默认值是vhd。</p>
</td>
</tr>
<tr id="row30993478171646"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p9133289171710"><a name="p9133289171710"></a><a name="p9133289171710"></a>min_ram</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p1598950171710"><a name="p1598950171710"></a><a name="p1598950171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p29186361172418"><a name="p29186361172418"></a><a name="p29186361172418"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p63030551172421"><a name="p63030551172421"></a><a name="p63030551172421"></a>镜像运行需要的最小内存，单位为MB。参数取值依据<span id="text1275714241386"><a name="text1275714241386"></a><a name="text1275714241386"></a></span><span id="text3257826103815"><a name="text3257826103815"></a><a name="text3257826103815"></a>云服务器</span>的规格限制，一般设置为0。</p>
<p id="p574912347473"><a name="p574912347473"></a><a name="p574912347473"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
</td>
</tr>
<tr id="row4294549416037"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p5603301516037"><a name="p5603301516037"></a><a name="p5603301516037"></a>min_disk</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p4238040516037"><a name="p4238040516037"></a><a name="p4238040516037"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p1026079116037"><a name="p1026079116037"></a><a name="p1026079116037"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p33012089153426"><a name="p33012089153426"></a><a name="p33012089153426"></a>镜像运行需要的最小磁盘，单位为GB 。取值为40～1024GB。</p>
</td>
</tr>
<tr id="row2123326171646"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p61378322171710"><a name="p61378322171710"></a><a name="p61378322171710"></a>__os_bit</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p5588210171710"><a name="p5588210171710"></a><a name="p5588210171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p20135377172418"><a name="p20135377172418"></a><a name="p20135377172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p46808977172421"><a name="p46808977172421"></a><a name="p46808977172421"></a>操作系统位数，一般取值为32或者64。</p>
</td>
</tr>
<tr id="row44306200171658"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p3969636171710"><a name="p3969636171710"></a><a name="p3969636171710"></a>__platform</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p53105072171710"><a name="p53105072171710"></a><a name="p53105072171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p10760011172418"><a name="p10760011172418"></a><a name="p10760011172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p2485190202218"><a name="p2485190202218"></a><a name="p2485190202218"></a>镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。</p>
</td>
</tr>
<tr id="row9909482171658"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p5556492171710"><a name="p5556492171710"></a><a name="p5556492171710"></a>marker</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p47422720171710"><a name="p47422720171710"></a><a name="p47422720171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p5646864172418"><a name="p5646864172418"></a><a name="p5646864172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p27827411172421"><a name="p27827411172421"></a><a name="p27827411172421"></a>用于分页，表示从哪个镜像开始查询，取值为镜像ID。</p>
</td>
</tr>
<tr id="row12166148171658"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p12628035171710"><a name="p12628035171710"></a><a name="p12628035171710"></a>limit</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p16237895171710"><a name="p16237895171710"></a><a name="p16237895171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p1378961172418"><a name="p1378961172418"></a><a name="p1378961172418"></a>Integer</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p19305703172421"><a name="p19305703172421"></a><a name="p19305703172421"></a>用于分页，表示查询几条镜像记录，取值为整数，默认返回25条镜像记录。</p>
</td>
</tr>
<tr id="row15101772171658"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p47145990171710"><a name="p47145990171710"></a><a name="p47145990171710"></a>sort_key</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p60728885171710"><a name="p60728885171710"></a><a name="p60728885171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p11895688172418"><a name="p11895688172418"></a><a name="p11895688172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p48105504172421"><a name="p48105504172421"></a><a name="p48105504172421"></a>用于排序，表示按照哪个字段排序。取值为镜像属性name、container_format、disk_format、status、id、size、create_at字段，默认为创建时间。</p>
</td>
</tr>
<tr id="row50874737171658"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p17835230171710"><a name="p17835230171710"></a><a name="p17835230171710"></a>sort_dir</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p35367554171710"><a name="p35367554171710"></a><a name="p35367554171710"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p6026804172418"><a name="p6026804172418"></a><a name="p6026804172418"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p38085944172421"><a name="p38085944172421"></a><a name="p38085944172421"></a>用于排序，表示升序还是降序，取值为asc和desc。与sort_key一起组合使用，默认为降序desc。</p>
</td>
</tr>
<tr id="row25115385114914"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p21080313114914"><a name="p21080313114914"></a><a name="p21080313114914"></a>__os_type</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p49589429114924"><a name="p49589429114924"></a><a name="p49589429114924"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p63675406114914"><a name="p63675406114914"></a><a name="p63675406114914"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p57434227114914"><a name="p57434227114914"></a><a name="p57434227114914"></a>镜像系统类型，取值为Linux、Windows、Other。</p>
</td>
</tr>
<tr id="row4436325311929"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p3665371811929"><a name="p3665371811929"></a><a name="p3665371811929"></a>tag</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p1616121311929"><a name="p1616121311929"></a><a name="p1616121311929"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p3398983911929"><a name="p3398983911929"></a><a name="p3398983911929"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p1525288141944"><a name="p1525288141944"></a><a name="p1525288141944"></a>标签，用户为镜像增加自定义标签后可以通过该参数过滤查询。</p>
<div class="note" id="note10170152764913"><a name="note10170152764913"></a><a name="note10170152764913"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p517019273499"><a name="p517019273499"></a><a name="p517019273499"></a>系统近期对标签功能进行了升级。如果之前添加的Tag为“Key.Value”的形式，则查询的时候需要使用“Key=Value”的格式来查询。例如：之前添加的tag为“a.b”,则升级后，查询时需使用“tag=a=b”。</p>
</div></div>
</td>
</tr>
<tr id="row43430748111132"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p28229739111132"><a name="p28229739111132"></a><a name="p28229739111132"></a>member_status</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p4907555111132"><a name="p4907555111132"></a><a name="p4907555111132"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p61967659111132"><a name="p61967659111132"></a><a name="p61967659111132"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p53324459111132"><a name="p53324459111132"></a><a name="p53324459111132"></a>成员状态。目前取值有accepted、rejected、pending。accepted表示已经接受共享的镜像，rejected表示已经拒绝了其他用户共享的镜像，pending表示需要确认的其他用户的共享镜像。需要在查询时，设置“visibility”参数为“shared”。</p>
</td>
</tr>
<tr id="row607872792117"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p2484690921449"><a name="p2484690921449"></a><a name="p2484690921449"></a>__support_kvm</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p6644261721449"><a name="p6644261721449"></a><a name="p6644261721449"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p1314289321449"><a name="p1314289321449"></a><a name="p1314289321449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p5794144221449"><a name="p5794144221449"></a><a name="p5794144221449"></a>如果镜像支持KVM，取值为true，否则无需增加该属性。</p>
</td>
</tr>
<tr id="row2242102211315"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p2101233521141"><a name="p2101233521141"></a><a name="p2101233521141"></a>__support_xen</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p2427761221141"><a name="p2427761221141"></a><a name="p2427761221141"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p2032954521141"><a name="p2032954521141"></a><a name="p2032954521141"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p3608043021141"><a name="p3608043021141"></a><a name="p3608043021141"></a>如果镜像支持XEN，取值为true，否则无需增加该属性。</p>
</td>
</tr>
<tr id="row14291359211318"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p16614938211414"><a name="p16614938211414"></a><a name="p16614938211414"></a>__support_largememory</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p3632756211414"><a name="p3632756211414"></a><a name="p3632756211414"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p25817810211414"><a name="p25817810211414"></a><a name="p25817810211414"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p10867869211414"><a name="p10867869211414"></a><a name="p10867869211414"></a>表示该镜像支持超大内存。如果镜像支持超大内存，取值为true，否则无需增加该属性。</p>
</td>
</tr>
<tr id="row52211464211322"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p6452067211434"><a name="p6452067211434"></a><a name="p6452067211434"></a>__support_diskintensive</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p52855412211434"><a name="p52855412211434"></a><a name="p52855412211434"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p53429945211434"><a name="p53429945211434"></a><a name="p53429945211434"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p16679154915811"><a name="p16679154915811"></a><a name="p16679154915811"></a>表示该镜像支持密集存储。如果镜像支持密集存储性能，则值为true，否则无需增加该属性。</p>
</td>
</tr>
<tr id="row13134583211325"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p35006343211449"><a name="p35006343211449"></a><a name="p35006343211449"></a>__support_highperformance</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p18255910211449"><a name="p18255910211449"></a><a name="p18255910211449"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p2333756211449"><a name="p2333756211449"></a><a name="p2333756211449"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p23586946211449"><a name="p23586946211449"></a><a name="p23586946211449"></a>表示该镜像支持高计算性能。如果镜像支持高计算性能，则值为true，否则无需增加该属性。</p>
</td>
</tr>
<tr id="row66912955211328"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p17122048211459"><a name="p17122048211459"></a><a name="p17122048211459"></a>__support_xen_gpu_type</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p44708641211459"><a name="p44708641211459"></a><a name="p44708641211459"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p64630134211459"><a name="p64630134211459"></a><a name="p64630134211459"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p113841114719"><a name="p113841114719"></a><a name="p113841114719"></a>表示该镜像是支持XEN虚拟化平台下的GPU类型。支持GPU加速型实例的镜像操作系统类型请参考<a href="相关参数取值列表.md#table65768383152758">表2</a>。如果不支持XEN虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
</td>
</tr>
<tr id="row550534121153"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p17764802211519"><a name="p17764802211519"></a><a name="p17764802211519"></a>__support_kvm_gpu_type</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p29662897211519"><a name="p29662897211519"></a><a name="p29662897211519"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p53884489211519"><a name="p53884489211519"></a><a name="p53884489211519"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p23107258211519"><a name="p23107258211519"></a><a name="p23107258211519"></a>表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考<a href="相关参数取值列表.md#table282523154017">表3</a>。如果不支持KVM虚拟化下GPU类型，无需添加该属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
</td>
</tr>
<tr id="row48915660211510"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p866834211519"><a name="p866834211519"></a><a name="p866834211519"></a>__support_xen_hana</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p3104731211519"><a name="p3104731211519"></a><a name="p3104731211519"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p50156693211519"><a name="p50156693211519"></a><a name="p50156693211519"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p069717225820"><a name="p069717225820"></a><a name="p069717225820"></a>如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无需添加该属性。</p>
<p id="p56971922588"><a name="p56971922588"></a><a name="p56971922588"></a>该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
</td>
</tr>
<tr id="row135722301704"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p1677823711015"><a name="p1677823711015"></a><a name="p1677823711015"></a>__support_kvm_infiniband</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p147787374015"><a name="p147787374015"></a><a name="p147787374015"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p028830316"><a name="p028830316"></a><a name="p028830316"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p18515175113010"><a name="p18515175113010"></a><a name="p18515175113010"></a>如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无需添加该属性。</p>
<p id="p155169515013"><a name="p155169515013"></a><a name="p155169515013"></a>该属性与“__support_xen”属性不共存。</p>
</td>
</tr>
<tr id="row932118481247"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p14187217143019"><a name="p14187217143019"></a><a name="p14187217143019"></a>created_at</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p8313953143019"><a name="p8313953143019"></a><a name="p8313953143019"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p2341610143019"><a name="p2341610143019"></a><a name="p2341610143019"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p55452691143019"><a name="p55452691143019"></a><a name="p55452691143019"></a>镜像创建时间。支持按照时间点过滤查询，取值格式为“ 操作符:UTC时间”。</p>
<p id="p32947284143515"><a name="p32947284143515"></a><a name="p32947284143515"></a>其中操作符支持如下几种：</p>
<a name="ul638941319348"></a><a name="ul638941319348"></a><ul id="ul638941319348"><li>gt：大于</li><li>gte：大于等于</li><li>lt：小于</li><li>lte：小于等于</li><li>eq：等于</li><li>neq：不等于</li></ul>
<p id="p18028286143153"><a name="p18028286143153"></a><a name="p18028286143153"></a>时间格式支持：yyyy-MM-ddThh:mm:ssZ或者yyyy-MM-dd hh:mm:ss</p>
<p id="p47377274144446"><a name="p47377274144446"></a><a name="p47377274144446"></a>例如，查询创建时间在2018-10-28 10:00:00之前的镜像，可以通过如下条件过滤：</p>
<p id="p50025529144528"><a name="p50025529144528"></a><a name="p50025529144528"></a>created_at=lt:2018-10-28T10:00:00Z</p>
</td>
</tr>
<tr id="row82121252162418"><td class="cellrowborder" valign="top" width="19.16191619161916%" headers="mcps1.2.5.1.1 "><p id="p5543103144620"><a name="p5543103144620"></a><a name="p5543103144620"></a>updated_at</p>
</td>
<td class="cellrowborder" valign="top" width="17.241724172417243%" headers="mcps1.2.5.1.2 "><p id="p46338199144620"><a name="p46338199144620"></a><a name="p46338199144620"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="18.4018401840184%" headers="mcps1.2.5.1.3 "><p id="p62406652144620"><a name="p62406652144620"></a><a name="p62406652144620"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="45.1945194519452%" headers="mcps1.2.5.1.4 "><p id="p52031456144646"><a name="p52031456144646"></a><a name="p52031456144646"></a>镜像修改时间。支持按照时间点过滤查询，取值格式为 “ 操作符:UTC时间”。</p>
<p id="p65629927144646"><a name="p65629927144646"></a><a name="p65629927144646"></a>其中操作符支持如下几种：</p>
<a name="ul207912567349"></a><a name="ul207912567349"></a><ul id="ul207912567349"><li>gt：大于</li><li>gte：大于等于</li><li>lt：小于</li><li>lte：小于等于</li><li>eq：等于</li><li>neq：不等于</li></ul>
<p id="p37800263144646"><a name="p37800263144646"></a><a name="p37800263144646"></a>时间格式支持：yyyy-MM-ddThh:mm:ssZ或者yyyy-MM-dd hh:mm:ss</p>
<p id="p4658051144646"><a name="p4658051144646"></a><a name="p4658051144646"></a>例如，查询修改时间在2018-10-28 10:00:00之前的镜像，可以通过如下条件过滤：</p>
<p id="p41922462144646"><a name="p41922462144646"></a><a name="p41922462144646"></a>updated_at=lt:2018-10-28T10:00:00Z</p>
</td>
</tr>
</tbody>
</table>

## 常用列表查询方法<a name="section105891407155"></a>

-   公共镜像列表查询

    GET /v2/images?\_\_imagetype=gold&visibility=public&protected=true

-   私有镜像列表查询

    GET /v2/images?owner=\{project\_id\}

-   可以使用的共享镜像列表

    GET /v2/images?member\_status=accepted&visibility=shared&\_\_imagetype=shared

-   被拒绝的共享镜像列表

    GET /v2/images?member\_status=rejected&visibility=shared&\_\_imagetype=shared

-   未接受的共享镜像列表

    GET /v2/images?member\_status=pending&visibility=shared&\_\_imagetype=shared


## 请求消息<a name="section52453505"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images
    ```


## 响应消息<a name="section10077261173340"></a>

-   响应参数

    <a name="table535532255119"></a>
    <table><thead align="left"><tr id="row2355142212512"><th class="cellrowborder" valign="top" width="25.132513251325133%" id="mcps1.1.4.1.1"><p id="p38981352165112"><a name="p38981352165112"></a><a name="p38981352165112"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.082508250825086%" id="mcps1.1.4.1.2"><p id="p1889845215110"><a name="p1889845215110"></a><a name="p1889845215110"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.784978497849785%" id="mcps1.1.4.1.3"><p id="p1089810526511"><a name="p1089810526511"></a><a name="p1089810526511"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row103551922145118"><td class="cellrowborder" valign="top" width="25.132513251325133%" headers="mcps1.1.4.1.1 "><p id="p31509198115122"><a name="p31509198115122"></a><a name="p31509198115122"></a>first</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.082508250825086%" headers="mcps1.1.4.1.2 "><p id="p1978441285118"><a name="p1978441285118"></a><a name="p1978441285118"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.784978497849785%" headers="mcps1.1.4.1.3 "><p id="p10564152015112"><a name="p10564152015112"></a><a name="p10564152015112"></a>查询首页的URL。</p>
    </td>
    </tr>
    <tr id="row921220307515"><td class="cellrowborder" valign="top" width="25.132513251325133%" headers="mcps1.1.4.1.1 "><p id="p65807153115133"><a name="p65807153115133"></a><a name="p65807153115133"></a>next</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.082508250825086%" headers="mcps1.1.4.1.2 "><p id="p19798812175111"><a name="p19798812175111"></a><a name="p19798812175111"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.784978497849785%" headers="mcps1.1.4.1.3 "><p id="p556472025120"><a name="p556472025120"></a><a name="p556472025120"></a>查询下一页的URL。当查询镜像列表最后一页时，不存在next。</p>
    </td>
    </tr>
    <tr id="row7658173612513"><td class="cellrowborder" valign="top" width="25.132513251325133%" headers="mcps1.1.4.1.1 "><p id="p37867696115128"><a name="p37867696115128"></a><a name="p37867696115128"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.082508250825086%" headers="mcps1.1.4.1.2 "><p id="p1781511129513"><a name="p1781511129513"></a><a name="p1781511129513"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.784978497849785%" headers="mcps1.1.4.1.3 "><p id="p195811620145120"><a name="p195811620145120"></a><a name="p195811620145120"></a>描述镜像列表模式的URL。</p>
    </td>
    </tr>
    <tr id="row111779195515"><td class="cellrowborder" valign="top" width="25.132513251325133%" headers="mcps1.1.4.1.1 "><p id="p31333900172519"><a name="p31333900172519"></a><a name="p31333900172519"></a>images</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.082508250825086%" headers="mcps1.1.4.1.2 "><p id="p778421215514"><a name="p778421215514"></a><a name="p778421215514"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.784978497849785%" headers="mcps1.1.4.1.3 "><p id="p154910205516"><a name="p154910205516"></a><a name="p154910205516"></a>资源类型。</p>
    <p id="p1635917815564"><a name="p1635917815564"></a><a name="p1635917815564"></a>具体请参见<a href="#table13195036194916">表2</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  images字段说明

    <a name="table13195036194916"></a>
    <table><thead align="left"><tr id="row60394066194916"><th class="cellrowborder" valign="top" width="25.069999999999997%" id="mcps1.2.4.1.1"><p id="p60081139194916"><a name="p60081139194916"></a><a name="p60081139194916"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.3%" id="mcps1.2.4.1.2"><p id="p61997487194916"><a name="p61997487194916"></a><a name="p61997487194916"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.63%" id="mcps1.2.4.1.3"><p id="p55740570194916"><a name="p55740570194916"></a><a name="p55740570194916"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row88721329162210"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p20872112919226"><a name="p20872112919226"></a><a name="p20872112919226"></a>__backup_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p587216290228"><a name="p587216290228"></a><a name="p587216290228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p28721629182213"><a name="p28721629182213"></a><a name="p28721629182213"></a>备份ID。如果是备份创建的镜像，则填写为备份的ID，否则无此参数。</p>
    </td>
    </tr>
    <tr id="row14392163492214"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p15392634152214"><a name="p15392634152214"></a><a name="p15392634152214"></a>__data_origin</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p839223462213"><a name="p839223462213"></a><a name="p839223462213"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p83925347225"><a name="p83925347225"></a><a name="p83925347225"></a>镜像来源。公共镜像为空。</p>
    </td>
    </tr>
    <tr id="row1239210341224"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p7392163492218"><a name="p7392163492218"></a><a name="p7392163492218"></a>__description</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p839215343223"><a name="p839215343223"></a><a name="p839215343223"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1239253416227"><a name="p1239253416227"></a><a name="p1239253416227"></a>镜像描述信息。</p>
    </td>
    </tr>
    <tr id="row168361029112413"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p8836929112412"><a name="p8836929112412"></a><a name="p8836929112412"></a>__image_location</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p283672918249"><a name="p283672918249"></a><a name="p283672918249"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p6836162932416"><a name="p6836162932416"></a><a name="p6836162932416"></a>镜像的存储位置。</p>
    </td>
    </tr>
    <tr id="row1369611116251"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p769614114257"><a name="p769614114257"></a><a name="p769614114257"></a>__image_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p169619113254"><a name="p169619113254"></a><a name="p169619113254"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p9696191113254"><a name="p9696191113254"></a><a name="p9696191113254"></a>镜像文件的大小，单位为字节。目前取值为大于0的字符串。</p>
    </td>
    </tr>
    <tr id="row16696201162516"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p869615113253"><a name="p869615113253"></a><a name="p869615113253"></a>__image_source_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p3696111152513"><a name="p3696111152513"></a><a name="p3696111152513"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1869671119255"><a name="p1869671119255"></a><a name="p1869671119255"></a>镜像后端存储类型，目前只支持uds。</p>
    </td>
    </tr>
    <tr id="row176961611192514"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p06969118257"><a name="p06969118257"></a><a name="p06969118257"></a>__is_config_init</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p2696181162519"><a name="p2696181162519"></a><a name="p2696181162519"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p36961511122510"><a name="p36961511122510"></a><a name="p36961511122510"></a>是否完成了初始化配置。取值为“true”或“false”。</p>
    </td>
    </tr>
    <tr id="row18692334194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p37684049194916"><a name="p37684049194916"></a><a name="p37684049194916"></a>__isregistered</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p15996779194916"><a name="p15996779194916"></a><a name="p15996779194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p20670704194916"><a name="p20670704194916"></a><a name="p20670704194916"></a>镜像是否可用，取值为true，扩展接口会默认为true，普通用户只能查询取值为true的镜像。</p>
    </td>
    </tr>
    <tr id="row1083631010288"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p08364101286"><a name="p08364101286"></a><a name="p08364101286"></a>__lazyloading</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p1383612108285"><a name="p1383612108285"></a><a name="p1383612108285"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1983615107285"><a name="p1983615107285"></a><a name="p1983615107285"></a>镜像是否支持延迟加载。</p>
    </td>
    </tr>
    <tr id="row17545174132818"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1354584112810"><a name="p1354584112810"></a><a name="p1354584112810"></a>__originalimagename</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p16545154115289"><a name="p16545154115289"></a><a name="p16545154115289"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1546541202818"><a name="p1546541202818"></a><a name="p1546541202818"></a>父镜像ID。公共镜像或通过文件创建的私有镜像，取值为空。</p>
    </td>
    </tr>
    <tr id="row51818614194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p36558171194916"><a name="p36558171194916"></a><a name="p36558171194916"></a>__imagetype</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p11081443194916"><a name="p11081443194916"></a><a name="p11081443194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p25181653194916"><a name="p25181653194916"></a><a name="p25181653194916"></a>镜像类型，目前支持以下类型：</p>
    <a name="ul25308291194916"></a><a name="ul25308291194916"></a><ul id="ul25308291194916"><li>公共镜像：gold</li><li>私有镜像：private</li><li>共享镜像：shared</li></ul>
    </td>
    </tr>
    <tr id="row20369060194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p39281165194916"><a name="p39281165194916"></a><a name="p39281165194916"></a>protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p25691866194916"><a name="p25691866194916"></a><a name="p25691866194916"></a>Boolean</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p666381194916"><a name="p666381194916"></a><a name="p666381194916"></a>镜像是否是受保护，查询公共镜像时候取值为true，查询私有镜像可以不指定。</p>
    </td>
    </tr>
    <tr id="row104049273291"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1440422732919"><a name="p1440422732919"></a><a name="p1440422732919"></a>virtual_env_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p104042275299"><a name="p104042275299"></a><a name="p104042275299"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p840492752919"><a name="p840492752919"></a><a name="p840492752919"></a>镜像使用的环境类型：FusionCompute、Ironic、DataImage、IsoImage。</p>
    <a name="ul20526189153516"></a><a name="ul20526189153516"></a><ul id="ul20526189153516"><li>如果是<span id="text596261823114"><a name="text596261823114"></a><a name="text596261823114"></a></span><span id="text1096261819311"><a name="text1096261819311"></a><a name="text1096261819311"></a>云服务器</span>镜像（即系统盘镜像），则取值为FusionCompute。</li><li>如果是数据卷镜像，则取值是DataImage。</li><li>如果是<span id="text11666743203118"><a name="text11666743203118"></a><a name="text11666743203118"></a></span><span id="text15705204519311"><a name="text15705204519311"></a><a name="text15705204519311"></a>裸金属服务器</span>镜像，则取值是Ironic。</li><li>如果是ISO镜像，则取值是IsoImage。</li></ul>
    </td>
    </tr>
    <tr id="row184042274291"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1140414275295"><a name="p1140414275295"></a><a name="p1140414275295"></a>virtual_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p16404132718291"><a name="p16404132718291"></a><a name="p16404132718291"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1440418275296"><a name="p1440418275296"></a><a name="p1440418275296"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row5997430194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p16029804194916"><a name="p16029804194916"></a><a name="p16029804194916"></a>visibility</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p11960319194916"><a name="p11960319194916"></a><a name="p11960319194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p15545818173013"><a name="p15545818173013"></a><a name="p15545818173013"></a>是否被其他租户可见。取值如下：</p>
    <a name="ul2480149153015"></a><a name="ul2480149153015"></a><ul id="ul2480149153015"><li>public：表示公共镜像。</li><li>private：表示私有镜像。</li><li>shared：表示共享镜像。</li></ul>
    </td>
    </tr>
    <tr id="row62029643194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p58345161194916"><a name="p58345161194916"></a><a name="p58345161194916"></a>owner</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p13641590194916"><a name="p13641590194916"></a><a name="p13641590194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p31226997194916"><a name="p31226997194916"></a><a name="p31226997194916"></a>镜像属于哪个租户。</p>
    </td>
    </tr>
    <tr id="row12607524194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p14576499194916"><a name="p14576499194916"></a><a name="p14576499194916"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p6281007194916"><a name="p6281007194916"></a><a name="p6281007194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p38999531194916"><a name="p38999531194916"></a><a name="p38999531194916"></a>镜像ID。</p>
    </td>
    </tr>
    <tr id="row15451466194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p43609220194916"><a name="p43609220194916"></a><a name="p43609220194916"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p35010019194916"><a name="p35010019194916"></a><a name="p35010019194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p17239254194916"><a name="p17239254194916"></a><a name="p17239254194916"></a>镜像状态。取值如下：</p>
    <a name="ul20935566194916"></a><a name="ul20935566194916"></a><ul id="ul20935566194916"><li>queued：表示镜像元数据已经创建成功，等待上传镜像文件。</li><li>saving：表示镜像正在上传文件到后端存储。</li><li>deleted：表示镜像已经删除。</li><li>killed：表示镜像上传错误。</li><li>active：表示镜像可以正常使用。</li></ul>
    </td>
    </tr>
    <tr id="row39884627194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p9429320194916"><a name="p9429320194916"></a><a name="p9429320194916"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p58506224194916"><a name="p58506224194916"></a><a name="p58506224194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p41383666194916"><a name="p41383666194916"></a><a name="p41383666194916"></a>镜像名称。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row15180307194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p21645353194916"><a name="p21645353194916"></a><a name="p21645353194916"></a>container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p12805641194916"><a name="p12805641194916"></a><a name="p12805641194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p30624037194916"><a name="p30624037194916"></a><a name="p30624037194916"></a>容器类型。</p>
    </td>
    </tr>
    <tr id="row7180877194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p44780194194916"><a name="p44780194194916"></a><a name="p44780194194916"></a>disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p251278194916"><a name="p251278194916"></a><a name="p251278194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p20353524194916"><a name="p20353524194916"></a><a name="p20353524194916"></a>镜像格式，目前支持vhd、zvhd、raw、qcow2。默认值是vhd。</p>
    </td>
    </tr>
    <tr id="row48963992194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p6660406194916"><a name="p6660406194916"></a><a name="p6660406194916"></a>min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p11056800194916"><a name="p11056800194916"></a><a name="p11056800194916"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p23185596194916"><a name="p23185596194916"></a><a name="p23185596194916"></a>镜像运行需要的最小内存，单位为MB。参数取值依据<span id="text144715414413"><a name="text144715414413"></a><a name="text144715414413"></a></span><span id="text565265154413"><a name="text565265154413"></a><a name="text565265154413"></a>云服务器</span>的规格限制，一般为0。</p>
    <p id="p1277912311504"><a name="p1277912311504"></a><a name="p1277912311504"></a>云服务器的规格限制，请参见<a href="https://support.huaweicloud.com/productdesc-ecs/zh-cn_topic_0159822360.html" target="_blank" rel="noopener noreferrer">规格清单</a>。</p>
    </td>
    </tr>
    <tr id="row147225239"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1272151332"><a name="p1272151332"></a><a name="p1272151332"></a>max_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p872451437"><a name="p872451437"></a><a name="p872451437"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p4729515310"><a name="p4729515310"></a><a name="p4729515310"></a>镜像支持的最大内存，单位为MB。</p>
    </td>
    </tr>
    <tr id="row7343772194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p57974621194916"><a name="p57974621194916"></a><a name="p57974621194916"></a>min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p65558873194916"><a name="p65558873194916"></a><a name="p65558873194916"></a>Integer</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p8668516194916"><a name="p8668516194916"></a><a name="p8668516194916"></a>镜像运行需要的最小磁盘容量，单位为GB 。取值为40～1024GB。</p>
    </td>
    </tr>
    <tr id="row11115416194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p27933499194916"><a name="p27933499194916"></a><a name="p27933499194916"></a>__os_bit</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p64492127194916"><a name="p64492127194916"></a><a name="p64492127194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p56479792194916"><a name="p56479792194916"></a><a name="p56479792194916"></a>操作系统位数，一般取值为32或者64。</p>
    </td>
    </tr>
    <tr id="row1996681822919"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1996691822911"><a name="p1996691822911"></a><a name="p1996691822911"></a>__os_feature_list</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p596661818297"><a name="p596661818297"></a><a name="p596661818297"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p159661718142912"><a name="p159661718142912"></a><a name="p159661718142912"></a>镜像附加属性。该属性采用JSON格式来标识镜像支持的高级特性清单。</p>
    </td>
    </tr>
    <tr id="row38556080194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p36034782194916"><a name="p36034782194916"></a><a name="p36034782194916"></a>__platform</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p66792165194916"><a name="p66792165194916"></a><a name="p66792165194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p608798220230"><a name="p608798220230"></a><a name="p608798220230"></a>镜像平台分类，取值为Windows、Ubuntu、RedHat、SUSE、CentOS、Debian、OpenSUSE、Oracle Linux、Fedora、Other、CoreOS和EulerOS。</p>
    </td>
    </tr>
    <tr id="row172371922613"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p223872466"><a name="p223872466"></a><a name="p223872466"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p122387213610"><a name="p122387213610"></a><a name="p122387213610"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1423812364"><a name="p1423812364"></a><a name="p1423812364"></a>镜像视图。</p>
    </td>
    </tr>
    <tr id="row112385210618"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p112382219615"><a name="p112382219615"></a><a name="p112382219615"></a>self</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p20238202469"><a name="p20238202469"></a><a name="p20238202469"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p142381021865"><a name="p142381021865"></a><a name="p142381021865"></a>镜像链接信息。</p>
    </td>
    </tr>
    <tr id="row1323852462"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1023812210614"><a name="p1023812210614"></a><a name="p1023812210614"></a>size</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p122384220610"><a name="p122384220610"></a><a name="p122384220610"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p192384213614"><a name="p192384213614"></a><a name="p192384213614"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row65790409194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p27422885194916"><a name="p27422885194916"></a><a name="p27422885194916"></a>__os_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p2689444194916"><a name="p2689444194916"></a><a name="p2689444194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p16518422194916"><a name="p16518422194916"></a><a name="p16518422194916"></a>镜像系统类型，取值为Linux、Windows、Other。</p>
    </td>
    </tr>
    <tr id="row456017114307"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p356011173012"><a name="p356011173012"></a><a name="p356011173012"></a>__os_version</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p15607193014"><a name="p15607193014"></a><a name="p15607193014"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p12560151143012"><a name="p12560151143012"></a><a name="p12560151143012"></a>操作系统具体版本。</p>
    </td>
    </tr>
    <tr id="row14448077194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p29443552194916"><a name="p29443552194916"></a><a name="p29443552194916"></a>tags</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p39840346194916"><a name="p39840346194916"></a><a name="p39840346194916"></a>Array of strings</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p5842575194916"><a name="p5842575194916"></a><a name="p5842575194916"></a>镜像标签列表，提供用户可以自定义管理私有镜像的能力。</p>
    </td>
    </tr>
    <tr id="row17193106194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p50464322194916"><a name="p50464322194916"></a><a name="p50464322194916"></a>__support_kvm</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p48394540194916"><a name="p48394540194916"></a><a name="p48394540194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p27643702194916"><a name="p27643702194916"></a><a name="p27643702194916"></a>如果镜像支持KVM，取值为true，否则无此属性。</p>
    </td>
    </tr>
    <tr id="row47466733194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p19600163194916"><a name="p19600163194916"></a><a name="p19600163194916"></a>__support_xen</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p16086851194916"><a name="p16086851194916"></a><a name="p16086851194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p27966591194916"><a name="p27966591194916"></a><a name="p27966591194916"></a>如果镜像支持XEN，取值为true，否则无此属性。</p>
    </td>
    </tr>
    <tr id="row50372727194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p53659116194916"><a name="p53659116194916"></a><a name="p53659116194916"></a>__support_largememory</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p4364568194916"><a name="p4364568194916"></a><a name="p4364568194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p17985694194916"><a name="p17985694194916"></a><a name="p17985694194916"></a>表示该镜像支持超大内存。如果镜像支持超大内存，取值为true，否则无此属性。</p>
    </td>
    </tr>
    <tr id="row47555109194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p26758612194916"><a name="p26758612194916"></a><a name="p26758612194916"></a>__support_diskintensive</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p6470349194916"><a name="p6470349194916"></a><a name="p6470349194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p54336230194916"><a name="p54336230194916"></a><a name="p54336230194916"></a>表示该镜像支持密集存储。如果镜像支持密集存储性能，则值为true，否则无此属性。</p>
    </td>
    </tr>
    <tr id="row39158471194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p17719577194916"><a name="p17719577194916"></a><a name="p17719577194916"></a>__support_highperformance</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p29023139194916"><a name="p29023139194916"></a><a name="p29023139194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p2064082194916"><a name="p2064082194916"></a><a name="p2064082194916"></a>表示该镜像支持高计算性能。如果镜像支持高计算性能，则值为true，否则无此属性。</p>
    </td>
    </tr>
    <tr id="row32972949194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p53563221194916"><a name="p53563221194916"></a><a name="p53563221194916"></a>__support_xen_gpu_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p46282730194916"><a name="p46282730194916"></a><a name="p46282730194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p51460488194916"><a name="p51460488194916"></a><a name="p51460488194916"></a>表示该镜像是支持XEN虚拟化平台下的GPU类型。支持GPU加速型实例的镜像操作系统类型请参考<a href="相关参数取值列表.md#table65768383152758">表2</a>。如果不支持XEN虚拟化下GPU类型，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row7573455194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p9470103194916"><a name="p9470103194916"></a><a name="p9470103194916"></a>__support_kvm_gpu_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p57647928194916"><a name="p57647928194916"></a><a name="p57647928194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p15191025194916"><a name="p15191025194916"></a><a name="p15191025194916"></a>表示该镜像是支持KVM虚拟化平台下的GPU类型，取值参考<a href="相关参数取值列表.md#table282523154017">表3</a>。如果不支持KVM虚拟化下GPU类型，无此属性。该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row22513498194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p11654048194916"><a name="p11654048194916"></a><a name="p11654048194916"></a>__support_xen_hana</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p25213664194916"><a name="p25213664194916"></a><a name="p25213664194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p29040940194916"><a name="p29040940194916"></a><a name="p29040940194916"></a>如果镜像支持XEN虚拟化下HANA类型，取值为true。否则，无此属性。</p>
    <p id="p60041868194916"><a name="p60041868194916"></a><a name="p60041868194916"></a>该属性与“__support_xen”和“__support_kvm”属性不共存。</p>
    </td>
    </tr>
    <tr id="row31553169194916"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p5669919194916"><a name="p5669919194916"></a><a name="p5669919194916"></a>__support_kvm_infiniband</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p22029043194916"><a name="p22029043194916"></a><a name="p22029043194916"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p39522058194916"><a name="p39522058194916"></a><a name="p39522058194916"></a>如果镜像支持KVM虚拟化下Infiniband网卡类型，取值为true。否则，无此属性。</p>
    <p id="p20154205194916"><a name="p20154205194916"></a><a name="p20154205194916"></a>该属性与“__support_xen”属性不共存。</p>
    </td>
    </tr>
    <tr id="row16837133815306"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p4837143813015"><a name="p4837143813015"></a><a name="p4837143813015"></a>__productcode</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p1883718385300"><a name="p1883718385300"></a><a name="p1883718385300"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1183714385305"><a name="p1183714385305"></a><a name="p1183714385305"></a>市场镜像的产品ID。</p>
    </td>
    </tr>
    <tr id="row1867223234610"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1021161112333"><a name="p1021161112333"></a><a name="p1021161112333"></a>__root_origin</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p637311103320"><a name="p637311103320"></a><a name="p637311103320"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p937411163318"><a name="p937411163318"></a><a name="p937411163318"></a>表示当前镜像来源是从外部导入。取值样例：file。</p>
    </td>
    </tr>
    <tr id="row4531435114611"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1152411163311"><a name="p1152411163311"></a><a name="p1152411163311"></a>__sequence_num</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p95251143318"><a name="p95251143318"></a><a name="p95251143318"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p116891133317"><a name="p116891133317"></a><a name="p116891133317"></a>表示当前镜像对应<span id="text51784510454"><a name="text51784510454"></a><a name="text51784510454"></a></span><span id="text1553411467457"><a name="text1553411467457"></a><a name="text1553411467457"></a>云服务器</span>的系统盘插槽位置。</p>
    <p id="p468511113315"><a name="p468511113315"></a><a name="p468511113315"></a>取值样例：0。</p>
    </td>
    </tr>
    <tr id="row61293019200"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1613123052019"><a name="p1613123052019"></a><a name="p1613123052019"></a>__support_fc_inject</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p101393072018"><a name="p101393072018"></a><a name="p101393072018"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p8706203910588"><a name="p8706203910588"></a><a name="p8706203910588"></a>表示当前镜像支持Cloud-Init密码/密钥注入方式。</p>
    <p id="p1738141097"><a name="p1738141097"></a><a name="p1738141097"></a>如果取值为“true”，表示该镜像不支持Cloud-Init注入密码/密钥，其他取值时表示支持Cloud-Init注入密钥/密码。</p>
    <div class="note" id="note18419142317116"><a name="note18419142317116"></a><a name="note18419142317116"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p164199231519"><a name="p164199231519"></a><a name="p164199231519"></a>该特性参数只对ECS系统盘镜像生效，其他类型镜像不生效。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row654811718381"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1223217245352"><a name="p1223217245352"></a><a name="p1223217245352"></a>__is_offshelved</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p8232122410351"><a name="p8232122410351"></a><a name="p8232122410351"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p20232724133511"><a name="p20232724133511"></a><a name="p20232724133511"></a>表示当前市场镜像是否下架。</p>
    <a name="ul423215249355"></a><a name="ul423215249355"></a><ul id="ul423215249355"><li>true：已下架</li><li>false：未下架</li></ul>
    </td>
    </tr>
    <tr id="row27491393344"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p17494399345"><a name="p17494399345"></a><a name="p17494399345"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p1074973913413"><a name="p1074973913413"></a><a name="p1074973913413"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p4749143914346"><a name="p4749143914346"></a><a name="p4749143914346"></a>创建时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row10106116162612"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p31076672616"><a name="p31076672616"></a><a name="p31076672616"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p6107261266"><a name="p6107261266"></a><a name="p6107261266"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p610719611263"><a name="p610719611263"></a><a name="p610719611263"></a>更新时间。格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row510729153317"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p41042920339"><a name="p41042920339"></a><a name="p41042920339"></a>active_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p610529143316"><a name="p610529143316"></a><a name="p610529143316"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p10101329163315"><a name="p10101329163315"></a><a name="p10101329163315"></a>镜像状态变为正常的时间。</p>
    </td>
    </tr>
    <tr id="row51673215344"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p14167225346"><a name="p14167225346"></a><a name="p14167225346"></a>checksum</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p121671428341"><a name="p121671428341"></a><a name="p121671428341"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p11678213341"><a name="p11678213341"></a><a name="p11678213341"></a>目前暂时不使用。</p>
    </td>
    </tr>
    <tr id="row16942857114013"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p1630281818413"><a name="p1630281818413"></a><a name="p1630281818413"></a>hw_firmware_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p2030231864116"><a name="p2030231864116"></a><a name="p2030231864116"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p7302161874115"><a name="p7302161874115"></a><a name="p7302161874115"></a><span id="text1721618104620"><a name="text1721618104620"></a><a name="text1721618104620"></a></span><span id="text07221183460"><a name="text07221183460"></a><a name="text07221183460"></a>云服务器</span>的启动方式。目前支持：</p>
    <a name="ul730291810417"></a><a name="ul730291810417"></a><ul id="ul730291810417"><li>bios：表示bios引导启动。</li><li>uefi：表示uefi引导启动。</li></ul>
    </td>
    </tr>
    <tr id="row55531161422"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p12554963211"><a name="p12554963211"></a><a name="p12554963211"></a>file</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p7554861211"><a name="p7554861211"></a><a name="p7554861211"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p115544615220"><a name="p115544615220"></a><a name="p115544615220"></a>镜像文件下载和上传链接。</p>
    </td>
    </tr>
    <tr id="row11166135123815"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p17166651133820"><a name="p17166651133820"></a><a name="p17166651133820"></a>enterprise_project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p13166451103814"><a name="p13166451103814"></a><a name="p13166451103814"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p14331112212111"><a name="p14331112212111"></a><a name="p14331112212111"></a>表示当前镜像所属的企业项目。</p>
    <a name="ul991416471019"></a><a name="ul991416471019"></a><ul id="ul991416471019"><li>取值为0或无该值，表示属于default企业项目。</li><li>取值为UUID，表示属于该UUID对应的企业项目。</li></ul>
    </td>
    </tr>
    <tr id="row149421557144014"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p8303121824114"><a name="p8303121824114"></a><a name="p8303121824114"></a>__support_arm</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p8303171844113"><a name="p8303171844113"></a><a name="p8303171844113"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1303141824112"><a name="p1303141824112"></a><a name="p1303141824112"></a>是否是ARM架构类型的镜像。取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row990785851820"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p13420892132"><a name="p13420892132"></a><a name="p13420892132"></a>__support_agent_list</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p164204961315"><a name="p164204961315"></a><a name="p164204961315"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p74209991311"><a name="p74209991311"></a><a name="p74209991311"></a>镜像是否支持企业主机安全或主机监控。</p>
    <a name="ul2308507142"></a><a name="ul2308507142"></a><ul id="ul2308507142"><li>hss：企业主机安全</li><li>ces：主机监控</li></ul>
    <p id="p1260041621510"><a name="p1260041621510"></a><a name="p1260041621510"></a>取值样例：</p>
    <p id="p15600111615158"><a name="p15600111615158"></a><a name="p15600111615158"></a>"__support_agent_list": "hss,ces"</p>
    <div class="note" id="note16932135991718"><a name="note16932135991718"></a><a name="note16932135991718"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1493310591173"><a name="p1493310591173"></a><a name="p1493310591173"></a>如果查询结果无此字段，表示镜像不支持企业主机安全或主机监控。</p>
    </div></div>
    </td>
    </tr>
    <tr id="row17998588141"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p5998158141416"><a name="p5998158141416"></a><a name="p5998158141416"></a>__account_code</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p14998138101410"><a name="p14998138101410"></a><a name="p14998138101410"></a>string</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p499814810149"><a name="p499814810149"></a><a name="p499814810149"></a>收费镜像标识。</p>
    </td>
    </tr>
    <tr id="row737411735810"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p192771122195514"><a name="p192771122195514"></a><a name="p192771122195514"></a>__support_amd</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p14278172215558"><a name="p14278172215558"></a><a name="p14278172215558"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p227810227555"><a name="p227810227555"></a><a name="p227810227555"></a>是否是AMD架构类型的镜像。取值为“true”或者“false”。</p>
    </td>
    </tr>
    <tr id="row2019201914432"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="ims_03_0604_p1784710241674"><a name="ims_03_0604_p1784710241674"></a><a name="ims_03_0604_p1784710241674"></a>__system__cmkid</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="ims_03_0604_p6847152417713"><a name="ims_03_0604_p6847152417713"></a><a name="ims_03_0604_p6847152417713"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="ims_03_0604_p28479241671"><a name="ims_03_0604_p28479241671"></a><a name="ims_03_0604_p28479241671"></a>加密镜像所使用的密钥ID。</p>
    </td>
    </tr>
    <tr id="row156841338194416"><td class="cellrowborder" valign="top" width="25.069999999999997%" headers="mcps1.2.4.1.1 "><p id="p6742230114713"><a name="p6742230114713"></a><a name="p6742230114713"></a>hw_vif_multiqueue_enabled</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.3%" headers="mcps1.2.4.1.2 "><p id="p1574213024718"><a name="p1574213024718"></a><a name="p1574213024718"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.63%" headers="mcps1.2.4.1.3 "><p id="p1874217309476"><a name="p1874217309476"></a><a name="p1874217309476"></a>镜像是否支持网卡多队列。取值为“true”或者“false”。</p>
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
      "schema": "/v2/schemas/images",
      "next": "/v2/images?__isregistered=true&marker=0328c25e-c840-4496-81ac-c4e01b214b1f&__imagetype=gold&limit=2",
      "images": [
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
          "hw_firmware_type": "bios",
          "status": "active"
        },
        {
          "schema": "/v2/schemas/image",
          "min_disk": 100,
          "created_at": "2018-09-06T14:03:05Z",
          "__image_source_type": "uds",
          "container_format": "bare",
          "file": "/v2/images/0328c25e-c840-4496-81ac-c4e01b214b1f/file",
          "updated_at": "2018-09-25T14:27:40Z",
          "protected": true,
          "checksum": "d41d8cd98f00b204e9800998ecf8427e",
          "__support_kvm_fpga_type": "VU9P_COMMON",
          "id": "0328c25e-c840-4496-81ac-c4e01b214b1f",
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
          "name": "CentOS 7.3 64bit with sdx",
          "self": "/v2/images/0328c25e-c840-4496-81ac-c4e01b214b1f",
          "disk_format": "zvhd2",
          "virtual_size": null,
          "hw_firmware_type": "bios",
          "status": "active"
        }
      ],
      "first": "/v2/images?__isregistered=true&__imagetype=gold&limit=2"
    }
    ```


## 返回值<a name="section20875522"></a>

-   正常

    200

-   异常

    <a name="table25137814143431"></a>
    <table><thead align="left"><tr id="row38004410143431"><th class="cellrowborder" valign="top" width="47%" id="mcps1.1.3.1.1"><p id="p58458378143431"><a name="p58458378143431"></a><a name="p58458378143431"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53%" id="mcps1.1.3.1.2"><p id="p18261951143431"><a name="p18261951143431"></a><a name="p18261951143431"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2823028143431"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p27338693143431"><a name="p27338693143431"></a><a name="p27338693143431"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p54285918143431"><a name="p54285918143431"></a><a name="p54285918143431"></a>请求错误，具体返回错误码请参考<a href="错误码.md">错误码</a>。</p>
    </td>
    </tr>
    <tr id="row35083253143431"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p23171273143431"><a name="p23171273143431"></a><a name="p23171273143431"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p25148486143431"><a name="p25148486143431"></a><a name="p25148486143431"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row25009784143431"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p12526651143431"><a name="p12526651143431"></a><a name="p12526651143431"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p46109225143431"><a name="p46109225143431"></a><a name="p46109225143431"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row15098650192329"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p3586211192331"><a name="p3586211192331"></a><a name="p3586211192331"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p22047708192331"><a name="p22047708192331"></a><a name="p22047708192331"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row12329845143431"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p59193425143431"><a name="p59193425143431"></a><a name="p59193425143431"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p9066084143431"><a name="p9066084143431"></a><a name="p9066084143431"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row14485900143431"><td class="cellrowborder" valign="top" width="47%" headers="mcps1.1.3.1.1 "><p id="p32507226143431"><a name="p32507226143431"></a><a name="p32507226143431"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53%" headers="mcps1.1.3.1.2 "><p id="p7940519143431"><a name="p7940519143431"></a><a name="p7940519143431"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


