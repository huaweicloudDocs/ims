# 获取镜像成员列表（OpenStack原生）<a name="ZH-CN_TOPIC_0036994320"></a>

## 功能介绍<a name="section24723024"></a>

该接口用于共享镜像过程中，获取接受该镜像的成员列表。

## URI<a name="section21180630"></a>

GET /v2/images/\{image\_id\}/members

参数说明请参见[表1](#table27262282)。

**表 1**  参数说明

<a name="table27262282"></a>
<table><thead align="left"><tr id="row27551015"><th class="cellrowborder" valign="top" width="23.03%" id="mcps1.2.5.1.1"><p id="p17039762"><a name="p17039762"></a><a name="p17039762"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="21.91%" id="mcps1.2.5.1.2"><p id="p38043494"><a name="p38043494"></a><a name="p38043494"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21.75%" id="mcps1.2.5.1.3"><p id="p1119157921331"><a name="p1119157921331"></a><a name="p1119157921331"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="33.31%" id="mcps1.2.5.1.4"><p id="p61624137"><a name="p61624137"></a><a name="p61624137"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row25499238"><td class="cellrowborder" valign="top" width="23.03%" headers="mcps1.2.5.1.1 "><p id="p52172387"><a name="p52172387"></a><a name="p52172387"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="21.91%" headers="mcps1.2.5.1.2 "><p id="p65213800"><a name="p65213800"></a><a name="p65213800"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.75%" headers="mcps1.2.5.1.3 "><p id="p3410274521331"><a name="p3410274521331"></a><a name="p3410274521331"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="33.31%" headers="mcps1.2.5.1.4 "><p id="p47826462"><a name="p47826462"></a><a name="p47826462"></a>镜像ID</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section56407950"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members
    ```


## 响应消息<a name="section37909503"></a>

-   响应参数

    <a name="table3448659117582"></a>
    <table><thead align="left"><tr id="row1240616417582"><th class="cellrowborder" valign="top" width="27.947205279472048%" id="mcps1.1.4.1.1"><p id="p6537523417582"><a name="p6537523417582"></a><a name="p6537523417582"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="28.407159284071586%" id="mcps1.1.4.1.2"><p id="p3416692117582"><a name="p3416692117582"></a><a name="p3416692117582"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.645635436456345%" id="mcps1.1.4.1.3"><p id="p1605720117582"><a name="p1605720117582"></a><a name="p1605720117582"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2556488117582"><td class="cellrowborder" valign="top" width="27.947205279472048%" headers="mcps1.1.4.1.1 "><p id="p202041354101614"><a name="p202041354101614"></a><a name="p202041354101614"></a>members</p>
    </td>
    <td class="cellrowborder" valign="top" width="28.407159284071586%" headers="mcps1.1.4.1.2 "><p id="p102036546164"><a name="p102036546164"></a><a name="p102036546164"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.645635436456345%" headers="mcps1.1.4.1.3 "><p id="p1420210549169"><a name="p1420210549169"></a><a name="p1420210549169"></a>共享成员列表。</p>
    <p id="p05981305593"><a name="p05981305593"></a><a name="p05981305593"></a>详情请参见<a href="#table47745347163">表2</a>。</p>
    </td>
    </tr>
    <tr id="row5330047317582"><td class="cellrowborder" valign="top" width="27.947205279472048%" headers="mcps1.1.4.1.1 "><p id="p2237105217582"><a name="p2237105217582"></a><a name="p2237105217582"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="28.407159284071586%" headers="mcps1.1.4.1.2 "><p id="p939051217582"><a name="p939051217582"></a><a name="p939051217582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.645635436456345%" headers="mcps1.1.4.1.3 "><p id="p2243400117582"><a name="p2243400117582"></a><a name="p2243400117582"></a>共享视图。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  MemberInfo参数说明

    <a name="table47745347163"></a>
    <table><thead align="left"><tr id="row177518341163"><th class="cellrowborder" valign="top" width="27.447255274472553%" id="mcps1.2.4.1.1"><p id="p157751734151616"><a name="p157751734151616"></a><a name="p157751734151616"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="29.027097290270977%" id="mcps1.2.4.1.2"><p id="p377543421614"><a name="p377543421614"></a><a name="p377543421614"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.525647435256474%" id="mcps1.2.4.1.3"><p id="p14775103451614"><a name="p14775103451614"></a><a name="p14775103451614"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row877510347162"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p27752348167"><a name="p27752348167"></a><a name="p27752348167"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p57752347164"><a name="p57752347164"></a><a name="p57752347164"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p17755341167"><a name="p17755341167"></a><a name="p17755341167"></a>共享状态。</p>
    </td>
    </tr>
    <tr id="row2775113417167"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p577543414167"><a name="p577543414167"></a><a name="p577543414167"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p17775534161611"><a name="p17775534161611"></a><a name="p17775534161611"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p47756349164"><a name="p47756349164"></a><a name="p47756349164"></a>共享时间，格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row1477583419160"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p577523419160"><a name="p577523419160"></a><a name="p577523419160"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p187759346162"><a name="p187759346162"></a><a name="p187759346162"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p1277553417163"><a name="p1277553417163"></a><a name="p1277553417163"></a>更新时间，格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row8776634121612"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p2776113410160"><a name="p2776113410160"></a><a name="p2776113410160"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p197761034141614"><a name="p197761034141614"></a><a name="p197761034141614"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p7776143461612"><a name="p7776143461612"></a><a name="p7776143461612"></a>镜像ID。</p>
    </td>
    </tr>
    <tr id="row4776183417161"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p6776203420161"><a name="p6776203420161"></a><a name="p6776203420161"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p1377620348165"><a name="p1377620348165"></a><a name="p1377620348165"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p147761734171613"><a name="p147761734171613"></a><a name="p147761734171613"></a>成员ID。</p>
    </td>
    </tr>
    <tr id="row8776163481619"><td class="cellrowborder" valign="top" width="27.447255274472553%" headers="mcps1.2.4.1.1 "><p id="p37761534151618"><a name="p37761534151618"></a><a name="p37761534151618"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.027097290270977%" headers="mcps1.2.4.1.2 "><p id="p11776163431611"><a name="p11776163431611"></a><a name="p11776163431611"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.525647435256474%" headers="mcps1.2.4.1.3 "><p id="p7776123401620"><a name="p7776123401620"></a><a name="p7776123401620"></a>共享视图。</p>
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
        "members": [
            {
                "status": "accepted",
                "created_at": "2016-09-01T02:05:14Z",
                "updated_at": "2016-09-01T02:37:11Z",
                "image_id": "d164b5df-1bc3-4c3f-893e-3e471fd16e64",
                "member_id": "edc89b490d7d4392898e19b2deb34797",
                "schema": "/v2/schemas/member"
            }
        ],
        "schema": "/v2/schemas/members"
    }
    ```


## 返回值<a name="section61374531"></a>

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


