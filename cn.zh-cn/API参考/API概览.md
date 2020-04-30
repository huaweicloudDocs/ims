# API概览<a name="ims_03_0200"></a>

镜像服务所提供的接口分为IMS接口与OpenStack原生接口。

通过配合使用镜像服务所提供的接口和OpenStack原生接口，您可以完整的使用镜像服务的所有功能。例如制作私有镜像，可以使用OpenStack原生接口，也可以使用IMS接口进行创建。

**表 1**  接口说明

<a name="table5876102613294"></a>
<table><thead align="left"><tr id="row3878122616298"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.4.1.1"><p id="p487811268290"><a name="p487811268290"></a><a name="p487811268290"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="p68781126182914"><a name="p68781126182914"></a><a name="p68781126182914"></a>子类型</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.4.1.3"><p id="p158781726112914"><a name="p158781726112914"></a><a name="p158781726112914"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row148781026122919"><td class="cellrowborder" rowspan="5" valign="top" width="17%" headers="mcps1.2.4.1.1 "><p id="p16878726162916"><a name="p16878726162916"></a><a name="p16878726162916"></a>IMS接口</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p128788265295"><a name="p128788265295"></a><a name="p128788265295"></a>镜像</p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.4.1.3 "><p id="p56591328178"><a name="p56591328178"></a><a name="p56591328178"></a>可以实现镜像的制作、镜像列表查询、镜像导出等操作。</p>
</td>
</tr>
<tr id="row1987820263297"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p8939172693215"><a name="p8939172693215"></a><a name="p8939172693215"></a>镜像标签</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p86434284717"><a name="p86434284717"></a><a name="p86434284717"></a>镜像标签可供给用户对私有镜像进行自定义标记。通过镜像标签，用户可以自由地对私有镜像分类管理。</p>
</td>
</tr>
<tr id="row87746166614"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p197741716567"><a name="p197741716567"></a><a name="p197741716567"></a>镜像共享</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1477491610610"><a name="p1477491610610"></a><a name="p1477491610610"></a>用户可以将私有镜像共享给其他用户使用。通过镜像共享的接口完成镜像共享的相关操作。</p>
</td>
</tr>
<tr id="row816313459617"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1216317451267"><a name="p1216317451267"></a><a name="p1216317451267"></a>镜像复制</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p7163194516616"><a name="p7163194516616"></a><a name="p7163194516616"></a>用户可以将一个已有镜像复制为另一个镜像。复制镜像时，可以更改镜像的加密等属性，以满足不同的场景。</p>
</td>
</tr>
<tr id="row132213492619"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1722949363"><a name="p1722949363"></a><a name="p1722949363"></a>镜像配额</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p15221849464"><a name="p15221849464"></a><a name="p15221849464"></a>查询租户在当前Region的私有镜像的配额数量。</p>
</td>
</tr>
<tr id="row9878726192911"><td class="cellrowborder" rowspan="4" valign="top" width="17%" headers="mcps1.2.4.1.1 "><p id="p1587832642913"><a name="p1587832642913"></a><a name="p1587832642913"></a>OpenStack原生接口</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p16101194212247"><a name="p16101194212247"></a><a name="p16101194212247"></a>镜像</p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.4.1.3 "><p id="p14101184217244"><a name="p14101184217244"></a><a name="p14101184217244"></a>可以实现镜像的制作、镜像列表查询、镜像导出等操作。</p>
</td>
</tr>
<tr id="row9878172662914"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1310194211243"><a name="p1310194211243"></a><a name="p1310194211243"></a>镜像标签</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1810154210242"><a name="p1810154210242"></a><a name="p1810154210242"></a>镜像标签可供给用户对私有镜像进行自定义标记。通过镜像标签，用户可以自由地对私有镜像分类管理。</p>
</td>
</tr>
<tr id="row117351143103220"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15101134272411"><a name="p15101134272411"></a><a name="p15101134272411"></a>镜像视图</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p610144252418"><a name="p610144252418"></a><a name="p610144252418"></a>镜像视图是提供给用户查询镜像属性的一些详情，比如取值类型，包含属性等。通过镜像视图，用户可以从宏观上对镜像基本情况有一定的了解。</p>
</td>
</tr>
<tr id="row11736144363213"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p51011542102411"><a name="p51011542102411"></a><a name="p51011542102411"></a>镜像共享</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p20101542202416"><a name="p20101542202416"></a><a name="p20101542202416"></a>用户可以将私有镜像共享给其他用户使用。通过镜像共享的接口完成镜像共享的相关操作。</p>
</td>
</tr>
</tbody>
</table>

