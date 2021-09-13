# API概览<a name="ims_03_0200"></a>

镜像服务所提供的接口分为IMS接口与OpenStack原生接口。

通过配合使用镜像服务提供的接口和OpenStack原生接口，您可以完整地使用镜像服务的所有功能。例如制作私有镜像，可以使用OpenStack原生接口，也可以使用IMS接口进行操作。

**表 1**  接口说明

<a name="table4640134110714"></a>
<table><thead align="left"><tr id="row1664020411271"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.4.1.1"><p id="p106401541376"><a name="p106401541376"></a><a name="p106401541376"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="19%" id="mcps1.2.4.1.2"><p id="p56405415716"><a name="p56405415716"></a><a name="p56405415716"></a>子类型</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.4.1.3"><p id="p864114419712"><a name="p864114419712"></a><a name="p864114419712"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1164114411774"><td class="cellrowborder" rowspan="5" valign="top" width="17%" headers="mcps1.2.4.1.1 "><p id="p13641114114720"><a name="p13641114114720"></a><a name="p13641114114720"></a>IMS接口</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p14641154113718"><a name="p14641154113718"></a><a name="p14641154113718"></a><a href="镜像.md">镜像</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.4.1.3 "><p id="p26417415711"><a name="p26417415711"></a><a name="p26417415711"></a>可以实现镜像的制作、镜像列表查询、镜像导出等操作。</p>
</td>
</tr>
<tr id="row126411411671"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p864164120716"><a name="p864164120716"></a><a name="p864164120716"></a><a href="镜像标签.md">镜像标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p16641941072"><a name="p16641941072"></a><a name="p16641941072"></a>对私有镜像进行自定义标记。通过镜像标签，用户可以自由地对私有镜像分类管理。</p>
</td>
</tr>
<tr id="row96411411712"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1964154113711"><a name="p1964154113711"></a><a name="p1964154113711"></a><a href="镜像共享.md">镜像共享</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p18641124111714"><a name="p18641124111714"></a><a name="p18641124111714"></a>用户可以将私有镜像共享给其他用户使用。通过镜像共享的接口完成镜像共享的相关操作。</p>
</td>
</tr>
<tr id="row1764118416719"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p96419411975"><a name="p96419411975"></a><a name="p96419411975"></a><a href="镜像复制.md">镜像复制</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p464110417712"><a name="p464110417712"></a><a name="p464110417712"></a>通过Region内复制镜像实现加密镜像与非加密镜像的转换；通过跨Region复制镜像实现镜像在两个区域间复制，帮助用户实现区域间的业务迁移。</p>
</td>
</tr>
<tr id="row19641541072"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p36419414716"><a name="p36419414716"></a><a name="p36419414716"></a><a href="镜像配额.md">镜像配额</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p1164194110711"><a name="p1164194110711"></a><a name="p1164194110711"></a>查询租户在当前Region的私有镜像的配额数量。</p>
</td>
</tr>
<tr id="row1641164110716"><td class="cellrowborder" rowspan="5" valign="top" width="17%" headers="mcps1.2.4.1.1 "><p id="p1464174110720"><a name="p1464174110720"></a><a name="p1464174110720"></a>OpenStack原生接口</p>
</td>
<td class="cellrowborder" valign="top" width="19%" headers="mcps1.2.4.1.2 "><p id="p166414411573"><a name="p166414411573"></a><a name="p166414411573"></a><a href="镜像（OpenStack原生）.md">镜像</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.4.1.3 "><p id="p1864117411975"><a name="p1864117411975"></a><a name="p1864117411975"></a>可以实现镜像的制作、镜像列表/详情查询、镜像导出等操作。</p>
</td>
</tr>
<tr id="row1064134117716"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p1764118416720"><a name="p1764118416720"></a><a name="p1764118416720"></a><a href="镜像标签（OpenStack原生）.md">镜像标签</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p206412411372"><a name="p206412411372"></a><a name="p206412411372"></a>对私有镜像进行自定义标记。通过镜像标签，用户可以自由地对私有镜像分类管理。</p>
</td>
</tr>
<tr id="row1364164110710"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p12641041375"><a name="p12641041375"></a><a name="p12641041375"></a><a href="镜像视图（OpenStack原生）.md">镜像视图</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p166419411872"><a name="p166419411872"></a><a name="p166419411872"></a>镜像视图是提供给用户查询镜像属性详情的接口，比如属性的取值类型、用途等。通过镜像视图，用户可以从宏观上对镜像的基本情况进行了解。</p>
</td>
</tr>
<tr id="row1264120411275"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p15641441772"><a name="p15641441772"></a><a name="p15641441772"></a><a href="镜像共享（OpenStack原生）.md">镜像共享</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p664174111719"><a name="p664174111719"></a><a name="p664174111719"></a>用户可以将私有镜像共享给其他用户使用。通过镜像共享的接口完成镜像共享的相关操作。</p>
</td>
</tr>
<tr id="row1475815206230"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p97581420152312"><a name="p97581420152312"></a><a name="p97581420152312"></a><a href="查询API版本信息（OpenStack原生）.md">查询API版本信息</a></p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p77589200233"><a name="p77589200233"></a><a name="p77589200233"></a>查询镜像服务当前所用的API版本。</p>
</td>
</tr>
</tbody>
</table>

