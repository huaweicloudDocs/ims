# 获取镜像成员列表（OpenStack原生）<a name="ZH-CN_TOPIC_0036994320"></a>

## 功能介绍<a name="section24723024"></a>

该接口用于共享镜像过程中，获取接受该镜像的成员列表。

## URI<a name="section21180630"></a>

-   URI格式

    GET /v2/images/\{image\_id\}/members

-   参数说明

    <a name="table27262282"></a>
    <table><thead align="left"><tr id="row27551015"><th class="cellrowborder" valign="top" width="25.75%" id="mcps1.1.5.1.1"><p id="p17039762"><a name="p17039762"></a><a name="p17039762"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="24.81%" id="mcps1.1.5.1.2"><p id="p38043494"><a name="p38043494"></a><a name="p38043494"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="18.61%" id="mcps1.1.5.1.3"><p id="p1119157921331"><a name="p1119157921331"></a><a name="p1119157921331"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="30.830000000000002%" id="mcps1.1.5.1.4"><p id="p61624137"><a name="p61624137"></a><a name="p61624137"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row25499238"><td class="cellrowborder" valign="top" width="25.75%" headers="mcps1.1.5.1.1 "><p id="p52172387"><a name="p52172387"></a><a name="p52172387"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.81%" headers="mcps1.1.5.1.2 "><p id="p65213800"><a name="p65213800"></a><a name="p65213800"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="18.61%" headers="mcps1.1.5.1.3 "><p id="p3410274521331"><a name="p3410274521331"></a><a name="p3410274521331"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="30.830000000000002%" headers="mcps1.1.5.1.4 "><p id="p47826462"><a name="p47826462"></a><a name="p47826462"></a>镜像ID</p>
    </td>
    </tr>
    </tbody>
    </table>


## 请求消息<a name="section56407950"></a>

请求样例

```
GET /v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members
```

## 响应<a name="section37909503"></a>

-   参数说明

    <a name="table3448659117582"></a>
    <table><thead align="left"><tr id="row1240616417582"><th class="cellrowborder" valign="top" width="30.486951304869514%" id="mcps1.1.4.1.1"><p id="p6537523417582"><a name="p6537523417582"></a><a name="p6537523417582"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.078292170782923%" id="mcps1.1.4.1.2"><p id="p3416692117582"><a name="p3416692117582"></a><a name="p3416692117582"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="52.434756524347556%" id="mcps1.1.4.1.3"><p id="p1605720117582"><a name="p1605720117582"></a><a name="p1605720117582"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row2556488117582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p5748949017582"><a name="p5748949017582"></a><a name="p5748949017582"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p3673160517582"><a name="p3673160517582"></a><a name="p3673160517582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p2247005617582"><a name="p2247005617582"></a><a name="p2247005617582"></a>共享状态</p>
    </td>
    </tr>
    <tr id="row90391417582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p610818017582"><a name="p610818017582"></a><a name="p610818017582"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p1177903017582"><a name="p1177903017582"></a><a name="p1177903017582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p1457734117582"><a name="p1457734117582"></a><a name="p1457734117582"></a>共享时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row6408721117582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p2368162517582"><a name="p2368162517582"></a><a name="p2368162517582"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p1812260517582"><a name="p1812260517582"></a><a name="p1812260517582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p5864490017582"><a name="p5864490017582"></a><a name="p5864490017582"></a>更新时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row5804205517582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p378601817582"><a name="p378601817582"></a><a name="p378601817582"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p978566117582"><a name="p978566117582"></a><a name="p978566117582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p5444103717582"><a name="p5444103717582"></a><a name="p5444103717582"></a>镜像ID</p>
    </td>
    </tr>
    <tr id="row2020728617582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p2617746417582"><a name="p2617746417582"></a><a name="p2617746417582"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p1876049317582"><a name="p1876049317582"></a><a name="p1876049317582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p4320497717582"><a name="p4320497717582"></a><a name="p4320497717582"></a>成员ID</p>
    </td>
    </tr>
    <tr id="row5330047317582"><td class="cellrowborder" valign="top" width="30.486951304869514%" headers="mcps1.1.4.1.1 "><p id="p2237105217582"><a name="p2237105217582"></a><a name="p2237105217582"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.078292170782923%" headers="mcps1.1.4.1.2 "><p id="p939051217582"><a name="p939051217582"></a><a name="p939051217582"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p2243400117582"><a name="p2243400117582"></a><a name="p2243400117582"></a>共享视图</p>
    </td>
    </tr>
    </tbody>
    </table>

-   响应样例：

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


