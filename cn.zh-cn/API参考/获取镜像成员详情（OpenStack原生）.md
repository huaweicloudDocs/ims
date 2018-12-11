# 获取镜像成员详情（OpenStack原生）<a name="ZH-CN_TOPIC_0036994319"></a>

## 功能介绍<a name="section16095919"></a>

该接口主要用于镜像共享中查询某个镜像成员的详情。

## URI<a name="section10645546"></a>

-   URI格式

    GET /v2/images/\{image\_id\}/members/\{member\_id\}

-   参数说明

    URI参数说明

    <a name="table30282311"></a>
    <table><thead align="left"><tr id="row19672999"><th class="cellrowborder" valign="top" width="30.826917308269174%" id="mcps1.1.5.1.1"><p id="p50009058"><a name="p50009058"></a><a name="p50009058"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.858214178582145%" id="mcps1.1.5.1.2"><p id="p24201902"><a name="p24201902"></a><a name="p24201902"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="20.48795120487951%" id="mcps1.1.5.1.3"><p id="p265296612135"><a name="p265296612135"></a><a name="p265296612135"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="30.826917308269174%" id="mcps1.1.5.1.4"><p id="p14197042"><a name="p14197042"></a><a name="p14197042"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row41227749"><td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.1.5.1.1 "><p id="p51113363"><a name="p51113363"></a><a name="p51113363"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.858214178582145%" headers="mcps1.1.5.1.2 "><p id="p46541742"><a name="p46541742"></a><a name="p46541742"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.48795120487951%" headers="mcps1.1.5.1.3 "><p id="p14189122135"><a name="p14189122135"></a><a name="p14189122135"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.1.5.1.4 "><p id="p11784733"><a name="p11784733"></a><a name="p11784733"></a>镜像ID</p>
    </td>
    </tr>
    <tr id="row2063059215392"><td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.1.5.1.1 "><p id="p6493862015397"><a name="p6493862015397"></a><a name="p6493862015397"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.858214178582145%" headers="mcps1.1.5.1.2 "><p id="p2553690515397"><a name="p2553690515397"></a><a name="p2553690515397"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="20.48795120487951%" headers="mcps1.1.5.1.3 "><p id="p5522341415397"><a name="p5522341415397"></a><a name="p5522341415397"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="30.826917308269174%" headers="mcps1.1.5.1.4 "><p id="p4391153115397"><a name="p4391153115397"></a><a name="p4391153115397"></a>成员ID。</p>
    </td>
    </tr>
    </tbody>
    </table>


## 请求<a name="section28701056"></a>

请求样例

```
GET /v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
```

## 响应<a name="section56982912"></a>

-   参数说明

    <a name="table16258230194835"></a>
    <table><thead align="left"><tr id="row23919935194835"><th class="cellrowborder" valign="top" width="34.21%" id="mcps1.1.4.1.1"><p id="p58466603194835"><a name="p58466603194835"></a><a name="p58466603194835"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.259999999999998%" id="mcps1.1.4.1.2"><p id="p38174436194835"><a name="p38174436194835"></a><a name="p38174436194835"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="49.53%" id="mcps1.1.4.1.3"><p id="p5121617194835"><a name="p5121617194835"></a><a name="p5121617194835"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row12197851194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p4684891915441"><a name="p4684891915441"></a><a name="p4684891915441"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p1716373215441"><a name="p1716373215441"></a><a name="p1716373215441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p4808503715441"><a name="p4808503715441"></a><a name="p4808503715441"></a>共享状态</p>
    </td>
    </tr>
    <tr id="row48777806194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p2316530815441"><a name="p2316530815441"></a><a name="p2316530815441"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p5311862715441"><a name="p5311862715441"></a><a name="p5311862715441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p764152715441"><a name="p764152715441"></a><a name="p764152715441"></a>共享时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row43890908194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p63809815441"><a name="p63809815441"></a><a name="p63809815441"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p2581736815441"><a name="p2581736815441"></a><a name="p2581736815441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p1083208215441"><a name="p1083208215441"></a><a name="p1083208215441"></a>更新时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row49474582194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p4485096415441"><a name="p4485096415441"></a><a name="p4485096415441"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p6192026915441"><a name="p6192026915441"></a><a name="p6192026915441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p4948586215441"><a name="p4948586215441"></a><a name="p4948586215441"></a>镜像ID</p>
    </td>
    </tr>
    <tr id="row12639379194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p3773344215441"><a name="p3773344215441"></a><a name="p3773344215441"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p451900915441"><a name="p451900915441"></a><a name="p451900915441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p3049545915441"><a name="p3049545915441"></a><a name="p3049545915441"></a>成员ID</p>
    </td>
    </tr>
    <tr id="row13178544194835"><td class="cellrowborder" valign="top" width="34.21%" headers="mcps1.1.4.1.1 "><p id="p1815619715441"><a name="p1815619715441"></a><a name="p1815619715441"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.259999999999998%" headers="mcps1.1.4.1.2 "><p id="p458118315441"><a name="p458118315441"></a><a name="p458118315441"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="49.53%" headers="mcps1.1.4.1.3 "><p id="p3553152415441"><a name="p3553152415441"></a><a name="p3553152415441"></a>共享视图</p>
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
        "status": "accepted",
        "created_at": "2016-09-01T02:05:14Z",
        "updated_at": "2016-09-01T02:37:11Z",
        "image_id": "d164b5df-1bc3-4c3f-893e-3e471fd16e64",
        "member_id": "edc89b490d7d4392898e19b2deb34797",
        "schema": "/v2/schemas/member"
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


