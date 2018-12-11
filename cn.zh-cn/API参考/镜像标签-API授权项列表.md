# 镜像标签<a name="ZH-CN_TOPIC_0125866391"></a>

<a name="table5223112534119"></a>
<table><thead align="left"><tr id="row1223122544113"><th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.1"><p id="p15664338411"><a name="p15664338411"></a><a name="p15664338411"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p10566633104119"><a name="p10566633104119"></a><a name="p10566633104119"></a>API功能</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p175661633164112"><a name="p175661633164112"></a><a name="p175661633164112"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.4"><p id="p1556643316414"><a name="p1556643316414"></a><a name="p1556643316414"></a>授权作用域</p>
</th>
</tr>
</thead>
<tbody><tr id="row1222332594115"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p165661233124120"><a name="p165661233124120"></a><a name="p165661233124120"></a>PUT /v2/images/{image_id}/tags/{tag}</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p9566153304119"><a name="p9566153304119"></a><a name="p9566153304119"></a>增加标签（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p856614334412"><a name="p856614334412"></a><a name="p856614334412"></a>ims:images:get</p>
<p id="p85661833124117"><a name="p85661833124117"></a><a name="p85661833124117"></a>ims:images:update</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul18566183394120"></a><a name="ul18566183394120"></a><ul id="ul18566183394120"><li>支持：<p id="p756633334116"><a name="p756633334116"></a><a name="p756633334116"></a>项目(Project)</p>
</li></ul>
<p id="p25661333184112"><a name="p25661333184112"></a><a name="p25661333184112"></a></p>
<a name="ul19566163312417"></a><a name="ul19566163312417"></a><ul id="ul19566163312417"><li>不支持：</li></ul>
<p id="p165668336417"><a name="p165668336417"></a><a name="p165668336417"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row22231125144111"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1256633314113"><a name="p1256633314113"></a><a name="p1256633314113"></a>DELETE /v2/images/{image_id}/tags/{tag}</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p18566633154116"><a name="p18566633154116"></a><a name="p18566633154116"></a>删除标签（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p65667335417"><a name="p65667335417"></a><a name="p65667335417"></a>ims:images:get</p>
<p id="p12566433104113"><a name="p12566433104113"></a><a name="p12566433104113"></a>ims:images:update</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul5566183313418"></a><a name="ul5566183313418"></a><ul id="ul5566183313418"><li>支持：<p id="p8566193394110"><a name="p8566193394110"></a><a name="p8566193394110"></a>项目(Project)</p>
</li></ul>
<p id="p856633394115"><a name="p856633394115"></a><a name="p856633394115"></a></p>
<a name="ul15566733104117"></a><a name="ul15566733104117"></a><ul id="ul15566733104117"><li>不支持：</li></ul>
<p id="p1456613344112"><a name="p1456613344112"></a><a name="p1456613344112"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row022382519417"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p25669338416"><a name="p25669338416"></a><a name="p25669338416"></a>PUT /v1/cloudimages/tags</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p256653318413"><a name="p256653318413"></a><a name="p256653318413"></a>增加或修改标签</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p456663315414"><a name="p456663315414"></a><a name="p456663315414"></a>ims:images:update</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul9566133394115"></a><a name="ul9566133394115"></a><ul id="ul9566133394115"><li>支持：<p id="p2566183334115"><a name="p2566183334115"></a><a name="p2566183334115"></a>项目(Project)</p>
</li></ul>
<p id="p756663314413"><a name="p756663314413"></a><a name="p756663314413"></a></p>
<a name="ul18566183317415"></a><a name="ul18566183317415"></a><ul id="ul18566183317415"><li>不支持：</li></ul>
<p id="p1056618332410"><a name="p1056618332410"></a><a name="p1056618332410"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row1223925144119"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p16566433194115"><a name="p16566433194115"></a><a name="p16566433194115"></a>GET /v1/cloudimages/tags</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p15666331418"><a name="p15666331418"></a><a name="p15666331418"></a>查询租户镜像标签列表</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p185667330416"><a name="p185667330416"></a><a name="p185667330416"></a>ims:images:list</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul656618333415"></a><a name="ul656618333415"></a><ul id="ul656618333415"><li>支持：<p id="p1556633344113"><a name="p1556633344113"></a><a name="p1556633344113"></a>项目(Project)</p>
</li></ul>
<p id="p95661033184117"><a name="p95661033184117"></a><a name="p95661033184117"></a></p>
<a name="ul1056663394111"></a><a name="ul1056663394111"></a><ul id="ul1056663394111"><li>不支持：</li></ul>
<p id="p25661933164119"><a name="p25661933164119"></a><a name="p25661933164119"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
</tbody>
</table>

