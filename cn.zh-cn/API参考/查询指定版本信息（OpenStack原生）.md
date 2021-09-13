# 查询指定版本信息（OpenStack原生）<a name="ims_03_0727"></a>

## 功能介绍<a name="section18441284152049"></a>

查询指定版本API的信息，包括该版本API的兼容性、域名信息等。

## URI<a name="section21923693152049"></a>

GET /\{api\_version\}

参数说明请参见[表1](#table6209770492526)。

**表 1**  参数说明

<a name="table6209770492526"></a>
<table><thead align="left"><tr id="row4392035892526"><th class="cellrowborder" valign="top" width="19.74%" id="mcps1.2.5.1.1"><p id="p77928492526"><a name="p77928492526"></a><a name="p77928492526"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.73%" id="mcps1.2.5.1.2"><p id="p6312205492526"><a name="p6312205492526"></a><a name="p6312205492526"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20.919999999999998%" id="mcps1.2.5.1.3"><p id="p1261277392526"><a name="p1261277392526"></a><a name="p1261277392526"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40.61%" id="mcps1.2.5.1.4"><p id="p1500168892526"><a name="p1500168892526"></a><a name="p1500168892526"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row717722492526"><td class="cellrowborder" valign="top" width="19.74%" headers="mcps1.2.5.1.1 "><p id="p4448425292526"><a name="p4448425292526"></a><a name="p4448425292526"></a>api_version</p>
</td>
<td class="cellrowborder" valign="top" width="18.73%" headers="mcps1.2.5.1.2 "><p id="p4645465392526"><a name="p4645465392526"></a><a name="p4645465392526"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="20.919999999999998%" headers="mcps1.2.5.1.3 "><p id="p473051492526"><a name="p473051492526"></a><a name="p473051492526"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="40.61%" headers="mcps1.2.5.1.4 "><p id="p4762733192526"><a name="p4762733192526"></a><a name="p4762733192526"></a>API版本号。例如：v2.0</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section62484847152049"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2.0
    ```


## 响应消息<a name="section47461859152049"></a>

-   响应参数

    <a name="table38630935152049"></a>
    <table><thead align="left"><tr id="row1849976152049"><th class="cellrowborder" valign="top" width="26.92269226922692%" id="mcps1.1.4.1.1"><p id="p15630386152049"><a name="p15630386152049"></a><a name="p15630386152049"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="26.842684268426847%" id="mcps1.1.4.1.2"><p id="p58101744152049"><a name="p58101744152049"></a><a name="p58101744152049"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="46.23462346234623%" id="mcps1.1.4.1.3"><p id="p27198362152049"><a name="p27198362152049"></a><a name="p27198362152049"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row55583702152049"><td class="cellrowborder" valign="top" width="26.92269226922692%" headers="mcps1.1.4.1.1 "><p id="p5985974152049"><a name="p5985974152049"></a><a name="p5985974152049"></a>versions</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.842684268426847%" headers="mcps1.1.4.1.2 "><p id="p15101858152049"><a name="p15101858152049"></a><a name="p15101858152049"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.23462346234623%" headers="mcps1.1.4.1.3 "><p id="p30612417152049"><a name="p30612417152049"></a><a name="p30612417152049"></a>版本信息。</p>
    <p id="p1025574924719"><a name="p1025574924719"></a><a name="p1025574924719"></a>详情请参见<a href="#table854484962011">表2</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  versions字段说明

    <a name="table854484962011"></a>
    <table><thead align="left"><tr id="row454414499200"><th class="cellrowborder" valign="top" width="27.222722272227223%" id="mcps1.2.4.1.1"><p id="p15544144932017"><a name="p15544144932017"></a><a name="p15544144932017"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="26.512651265126514%" id="mcps1.2.4.1.2"><p id="p1354414918206"><a name="p1354414918206"></a><a name="p1354414918206"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="46.26462646264626%" id="mcps1.2.4.1.3"><p id="p175441049112011"><a name="p175441049112011"></a><a name="p175441049112011"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3544134915207"><td class="cellrowborder" valign="top" width="27.222722272227223%" headers="mcps1.2.4.1.1 "><p id="p554412490205"><a name="p554412490205"></a><a name="p554412490205"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.512651265126514%" headers="mcps1.2.4.1.2 "><p id="p13544154992013"><a name="p13544154992013"></a><a name="p13544154992013"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.26462646264626%" headers="mcps1.2.4.1.3 "><p id="p13544549172014"><a name="p13544549172014"></a><a name="p13544549172014"></a>接口状态。</p>
    </td>
    </tr>
    <tr id="row1654434982010"><td class="cellrowborder" valign="top" width="27.222722272227223%" headers="mcps1.2.4.1.1 "><p id="p7544144912017"><a name="p7544144912017"></a><a name="p7544144912017"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.512651265126514%" headers="mcps1.2.4.1.2 "><p id="p7544849202011"><a name="p7544849202011"></a><a name="p7544849202011"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.26462646264626%" headers="mcps1.2.4.1.3 "><p id="p854474942018"><a name="p854474942018"></a><a name="p854474942018"></a>接口ID。</p>
    </td>
    </tr>
    <tr id="row13545134914208"><td class="cellrowborder" valign="top" width="27.222722272227223%" headers="mcps1.2.4.1.1 "><p id="p85451494204"><a name="p85451494204"></a><a name="p85451494204"></a>links</p>
    </td>
    <td class="cellrowborder" valign="top" width="26.512651265126514%" headers="mcps1.2.4.1.2 "><p id="p11545184910208"><a name="p11545184910208"></a><a name="p11545184910208"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.26462646264626%" headers="mcps1.2.4.1.3 "><p id="p454514493203"><a name="p454514493203"></a><a name="p454514493203"></a>自描述信息。</p>
    <p id="p1381418418482"><a name="p1381418418482"></a><a name="p1381418418482"></a>详情请参见<a href="#table9477147162314">表3</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3**  versions.links字段说明

    <a name="table9477147162314"></a>
    <table><thead align="left"><tr id="row147754713235"><th class="cellrowborder" valign="top" width="27.422742274227424%" id="mcps1.2.4.1.1"><p id="p147713470235"><a name="p147713470235"></a><a name="p147713470235"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="25.78257825782578%" id="mcps1.2.4.1.2"><p id="p1847764752313"><a name="p1847764752313"></a><a name="p1847764752313"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="46.79467946794679%" id="mcps1.2.4.1.3"><p id="p647724711236"><a name="p647724711236"></a><a name="p647724711236"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row15478104772314"><td class="cellrowborder" valign="top" width="27.422742274227424%" headers="mcps1.2.4.1.1 "><p id="p10478114720236"><a name="p10478114720236"></a><a name="p10478114720236"></a>href</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.78257825782578%" headers="mcps1.2.4.1.2 "><p id="p2478104702312"><a name="p2478104702312"></a><a name="p2478104702312"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.79467946794679%" headers="mcps1.2.4.1.3 "><p id="p1547818479233"><a name="p1547818479233"></a><a name="p1547818479233"></a>域名。</p>
    </td>
    </tr>
    <tr id="row181111958142415"><td class="cellrowborder" valign="top" width="27.422742274227424%" headers="mcps1.2.4.1.1 "><p id="p1911295882410"><a name="p1911295882410"></a><a name="p1911295882410"></a>rel</p>
    </td>
    <td class="cellrowborder" valign="top" width="25.78257825782578%" headers="mcps1.2.4.1.2 "><p id="p211211580241"><a name="p211211580241"></a><a name="p211211580241"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="46.79467946794679%" headers="mcps1.2.4.1.3 "><p id="p4112758122414"><a name="p4112758122414"></a><a name="p4112758122414"></a>域名描述。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   响应样例

    ```
    STATUS CODE 300
    ```

    ```
    {
        "versions": [
            {
                "status": "SUPPORTED",
                "id": "v2.0",
                "links": [
                    {
                        "href": "https://image.az1.dc1.domainname.com/v2/",
                        "rel": "self"
                    }
                ]
            }
        ]
    }
    ```


## 返回值<a name="section37588986152049"></a>

-   正常

    200

-   异常

    <a name="table271454817439"></a>
    <table><thead align="left"><tr id="row3541095017439"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p4971469317439"><a name="p4971469317439"></a><a name="p4971469317439"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p35835717439"><a name="p35835717439"></a><a name="p35835717439"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2902697417439"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p237466317439"><a name="p237466317439"></a><a name="p237466317439"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p5812997617439"><a name="p5812997617439"></a><a name="p5812997617439"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row5340773917439"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p3105962817439"><a name="p3105962817439"></a><a name="p3105962817439"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p3280197817439"><a name="p3280197817439"></a><a name="p3280197817439"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row2678235117439"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2188683517439"><a name="p2188683517439"></a><a name="p2188683517439"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2800317417439"><a name="p2800317417439"></a><a name="p2800317417439"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row16775501191954"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p19013873191957"><a name="p19013873191957"></a><a name="p19013873191957"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p63728762191957"><a name="p63728762191957"></a><a name="p63728762191957"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row5070198217439"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p1321988617439"><a name="p1321988617439"></a><a name="p1321988617439"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6417782617439"><a name="p6417782617439"></a><a name="p6417782617439"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row4072952517439"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p1075724317439"><a name="p1075724317439"></a><a name="p1075724317439"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6603036117439"><a name="p6603036117439"></a><a name="p6603036117439"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


