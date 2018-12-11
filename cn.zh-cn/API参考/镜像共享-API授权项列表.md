# 镜像共享<a name="ZH-CN_TOPIC_0125866393"></a>

<a name="table2116111104410"></a>
<table><thead align="left"><tr id="row811613124414"><th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.1"><p id="p53669173446"><a name="p53669173446"></a><a name="p53669173446"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.2"><p id="p93665171445"><a name="p93665171445"></a><a name="p93665171445"></a>API功能</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.3"><p id="p736610176441"><a name="p736610176441"></a><a name="p736610176441"></a>授权项</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.1.5.1.4"><p id="p1436616178441"><a name="p1436616178441"></a><a name="p1436616178441"></a>授权作用域</p>
</th>
</tr>
</thead>
<tbody><tr id="row911612114448"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1336621744412"><a name="p1336621744412"></a><a name="p1336621744412"></a>POST /v2/images/{image_id}/members</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p18366201710448"><a name="p18366201710448"></a><a name="p18366201710448"></a>添加镜像成员（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p036614178443"><a name="p036614178443"></a><a name="p036614178443"></a>ims:images:get</p>
<p id="p9366171712443"><a name="p9366171712443"></a><a name="p9366171712443"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul93661817134413"></a><a name="ul93661817134413"></a><ul id="ul93661817134413"><li>支持：<p id="p1036621734420"><a name="p1036621734420"></a><a name="p1036621734420"></a>项目(Project)</p>
</li></ul>
<p id="p03667173448"><a name="p03667173448"></a><a name="p03667173448"></a></p>
<a name="ul20366141712445"></a><a name="ul20366141712445"></a><ul id="ul20366141712445"><li>不支持：</li></ul>
<p id="p18366151717444"><a name="p18366151717444"></a><a name="p18366151717444"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row13116219446"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p153666175444"><a name="p153666175444"></a><a name="p153666175444"></a>PUT /v2/images/{image_id}/members/{member_id}</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p15366417164420"><a name="p15366417164420"></a><a name="p15366417164420"></a>更新镜像成员状态（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p11366131724411"><a name="p11366131724411"></a><a name="p11366131724411"></a>ims:images:get</p>
<p id="p236621794412"><a name="p236621794412"></a><a name="p236621794412"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul16366111714443"></a><a name="ul16366111714443"></a><ul id="ul16366111714443"><li>支持：<p id="p2366171784412"><a name="p2366171784412"></a><a name="p2366171784412"></a>项目(Project)</p>
</li></ul>
<p id="p6366181794411"><a name="p6366181794411"></a><a name="p6366181794411"></a></p>
<a name="ul1736611704419"></a><a name="ul1736611704419"></a><ul id="ul1736611704419"><li>不支持：</li></ul>
<p id="p436671774418"><a name="p436671774418"></a><a name="p436671774418"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row1711614104415"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1136611715441"><a name="p1136611715441"></a><a name="p1136611715441"></a>GET /v2/images/{image_id}/members/{member_id}</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1736671714446"><a name="p1736671714446"></a><a name="p1736671714446"></a>获取镜像成员详情（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p163661175444"><a name="p163661175444"></a><a name="p163661175444"></a>ims:images:get</p>
<p id="p0366191718440"><a name="p0366191718440"></a><a name="p0366191718440"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul7366141754413"></a><a name="ul7366141754413"></a><ul id="ul7366141754413"><li>支持：<p id="p9366131774416"><a name="p9366131774416"></a><a name="p9366131774416"></a>项目(Project)</p>
</li></ul>
<p id="p336681718443"><a name="p336681718443"></a><a name="p336681718443"></a></p>
<a name="ul5366131713448"></a><a name="ul5366131713448"></a><ul id="ul5366131713448"><li>不支持：</li></ul>
<p id="p236610179441"><a name="p236610179441"></a><a name="p236610179441"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row9116161104420"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1366151794418"><a name="p1366151794418"></a><a name="p1366151794418"></a>GET /v2/images/{image_id}/members</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1366171794413"><a name="p1366171794413"></a><a name="p1366171794413"></a>获取镜像成员列表（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p736615175448"><a name="p736615175448"></a><a name="p736615175448"></a>ims:images:get</p>
<p id="p43661817144419"><a name="p43661817144419"></a><a name="p43661817144419"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul4366141774415"></a><a name="ul4366141774415"></a><ul id="ul4366141774415"><li>支持：<p id="p1736691764411"><a name="p1736691764411"></a><a name="p1736691764411"></a>项目(Project)</p>
</li></ul>
<p id="p103661017174416"><a name="p103661017174416"></a><a name="p103661017174416"></a></p>
<a name="ul12366141719448"></a><a name="ul12366141719448"></a><ul id="ul12366141719448"><li>不支持：</li></ul>
<p id="p736691774414"><a name="p736691774414"></a><a name="p736691774414"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row211611119442"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1736611179444"><a name="p1736611179444"></a><a name="p1736611179444"></a>DELETE /v2/images/{image_id}/members/{member_id}</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p4366181712444"><a name="p4366181712444"></a><a name="p4366181712444"></a>删除指定的镜像成员（OpenStack 原生）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p10366917134414"><a name="p10366917134414"></a><a name="p10366917134414"></a>ims:images:get</p>
<p id="p193662017184412"><a name="p193662017184412"></a><a name="p193662017184412"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul836614178447"></a><a name="ul836614178447"></a><ul id="ul836614178447"><li>支持：<p id="p12366817144410"><a name="p12366817144410"></a><a name="p12366817144410"></a>项目(Project)</p>
</li></ul>
<p id="p93668177445"><a name="p93668177445"></a><a name="p93668177445"></a></p>
<a name="ul6366171718444"></a><a name="ul6366171718444"></a><ul id="ul6366171718444"><li>不支持：</li></ul>
<p id="p73661317124411"><a name="p73661317124411"></a><a name="p73661317124411"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row2116101154413"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1366417174414"><a name="p1366417174414"></a><a name="p1366417174414"></a>POST /v1/cloudimages/members</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p2366101774418"><a name="p2366101774418"></a><a name="p2366101774418"></a>批量添加镜像成员</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p1336616172440"><a name="p1336616172440"></a><a name="p1336616172440"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul103661170446"></a><a name="ul103661170446"></a><ul id="ul103661170446"><li>支持：<p id="p10366217154416"><a name="p10366217154416"></a><a name="p10366217154416"></a>项目(Project)</p>
</li></ul>
<p id="p1236631716449"><a name="p1236631716449"></a><a name="p1236631716449"></a></p>
<a name="ul1536631724417"></a><a name="ul1536631724417"></a><ul id="ul1536631724417"><li>不支持：</li></ul>
<p id="p18366101718442"><a name="p18366101718442"></a><a name="p18366101718442"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row1411611111442"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p1936671754412"><a name="p1936671754412"></a><a name="p1936671754412"></a>PUT /v1/cloudimages/members</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p153661417204414"><a name="p153661417204414"></a><a name="p153661417204414"></a>批量更新镜像成员状态</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p13366161744410"><a name="p13366161744410"></a><a name="p13366161744410"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul1036615179447"></a><a name="ul1036615179447"></a><ul id="ul1036615179447"><li>支持：<p id="p3366141754411"><a name="p3366141754411"></a><a name="p3366141754411"></a>项目(Project)</p>
</li></ul>
<p id="p33664173444"><a name="p33664173444"></a><a name="p33664173444"></a></p>
<a name="ul9366101704415"></a><a name="ul9366101704415"></a><ul id="ul9366101704415"><li>不支持：</li></ul>
<p id="p436614177444"><a name="p436614177444"></a><a name="p436614177444"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
<tr id="row1611614114415"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.1 "><p id="p4366817174414"><a name="p4366817174414"></a><a name="p4366817174414"></a>DELETE /v1/cloudimages/members</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.2 "><p id="p1036621754418"><a name="p1036621754418"></a><a name="p1036621754418"></a>批量删除镜像成员</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.3 "><p id="p173668177446"><a name="p173668177446"></a><a name="p173668177446"></a>ims:images:share</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.1.5.1.4 "><a name="ul14366417104411"></a><a name="ul14366417104411"></a><ul id="ul14366417104411"><li>支持：<p id="p1236641716441"><a name="p1236641716441"></a><a name="p1236641716441"></a>项目(Project)</p>
</li></ul>
<p id="p43661917164412"><a name="p43661917164412"></a><a name="p43661917164412"></a></p>
<a name="ul2036691716444"></a><a name="ul2036691716444"></a><ul id="ul2036691716444"><li>不支持：</li></ul>
<p id="p8366161719448"><a name="p8366161719448"></a><a name="p8366161719448"></a>企业项目(Enterprise Project)</p>
</td>
</tr>
</tbody>
</table>

