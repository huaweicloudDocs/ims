# 添加镜像成员（OpenStack原生）<a name="ims_03_0720"></a>

## 功能介绍<a name="section59471393"></a>

用户共享镜像给其他用户时，使用该接口向该镜像成员中添加接受镜像用户的项目ID。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=GlanceAddImageMember)中调试该接口。

## URI<a name="section65480490"></a>

POST /v2/images/\{image\_id\}/members

## 请求消息<a name="section52453505"></a>

-   请求参数

    <a name="table31018281142633"></a>
    <table><thead align="left"><tr id="row35509333142633"><th class="cellrowborder" valign="top" width="18.64%" id="mcps1.1.5.1.1"><p id="p57683706142633"><a name="p57683706142633"></a><a name="p57683706142633"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.05%" id="mcps1.1.5.1.2"><p id="p41868624142633"><a name="p41868624142633"></a><a name="p41868624142633"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.71%" id="mcps1.1.5.1.3"><p id="p35915390142633"><a name="p35915390142633"></a><a name="p35915390142633"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.599999999999994%" id="mcps1.1.5.1.4"><p id="p23465517142633"><a name="p23465517142633"></a><a name="p23465517142633"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row21658757142633"><td class="cellrowborder" valign="top" width="18.64%" headers="mcps1.1.5.1.1 "><p id="p9528877142633"><a name="p9528877142633"></a><a name="p9528877142633"></a>member</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.05%" headers="mcps1.1.5.1.2 "><p id="p33641549142633"><a name="p33641549142633"></a><a name="p33641549142633"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.71%" headers="mcps1.1.5.1.3 "><p id="p40610958142633"><a name="p40610958142633"></a><a name="p40610958142633"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.599999999999994%" headers="mcps1.1.5.1.4 "><p id="p19199817142646"><a name="p19199817142646"></a><a name="p19199817142646"></a>镜像成员。</p>
    <p id="p958017914274"><a name="p958017914274"></a><a name="p958017914274"></a>取值为目标用户的项目ID。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   请求样例

    ```
    POST https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members
    ```

    ```
    {
        "member":"edc89b490d7d4392898e19b2deb34797"
    }
    ```


## 响应消息<a name="section2319502"></a>

-   响应参数

    <a name="table170389018811"></a>
    <table><thead align="left"><tr id="row1730386618811"><th class="cellrowborder" valign="top" width="23.76%" id="mcps1.1.4.1.1"><p id="p5943589418811"><a name="p5943589418811"></a><a name="p5943589418811"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="21.61%" id="mcps1.1.4.1.2"><p id="p4957807018811"><a name="p4957807018811"></a><a name="p4957807018811"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="54.63%" id="mcps1.1.4.1.3"><p id="p5640070618811"><a name="p5640070618811"></a><a name="p5640070618811"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row25955412182112"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p30073002105145"><a name="p30073002105145"></a><a name="p30073002105145"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p8906282105145"><a name="p8906282105145"></a><a name="p8906282105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p50320231105145"><a name="p50320231105145"></a><a name="p50320231105145"></a>共享状态。</p>
    </td>
    </tr>
    <tr id="row3995446182130"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p42008850105145"><a name="p42008850105145"></a><a name="p42008850105145"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p3960824105145"><a name="p3960824105145"></a><a name="p3960824105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p52391359105145"><a name="p52391359105145"></a><a name="p52391359105145"></a>共享时间，格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row505449918811"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p8357119105145"><a name="p8357119105145"></a><a name="p8357119105145"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p3117216105145"><a name="p3117216105145"></a><a name="p3117216105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p51167945105145"><a name="p51167945105145"></a><a name="p51167945105145"></a>更新时间，格式为UTC时间。</p>
    </td>
    </tr>
    <tr id="row57822993182152"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p56013058105145"><a name="p56013058105145"></a><a name="p56013058105145"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p13537362105145"><a name="p13537362105145"></a><a name="p13537362105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p22784520105145"><a name="p22784520105145"></a><a name="p22784520105145"></a>镜像ID</p>
    </td>
    </tr>
    <tr id="row13561662182215"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p34026356105145"><a name="p34026356105145"></a><a name="p34026356105145"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p42845703105145"><a name="p42845703105145"></a><a name="p42845703105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p47949893105145"><a name="p47949893105145"></a><a name="p47949893105145"></a>成员ID，即接受镜像用户的项目ID。</p>
    </td>
    </tr>
    <tr id="row31851202182230"><td class="cellrowborder" valign="top" width="23.76%" headers="mcps1.1.4.1.1 "><p id="p58862775105145"><a name="p58862775105145"></a><a name="p58862775105145"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="21.61%" headers="mcps1.1.4.1.2 "><p id="p54265792105145"><a name="p54265792105145"></a><a name="p54265792105145"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="54.63%" headers="mcps1.1.4.1.3 "><p id="p33453007105145"><a name="p33453007105145"></a><a name="p33453007105145"></a>共享视图</p>
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
        "status": "pending",
        "created_at": "2016-09-01T02:05:14Z",
        "updated_at": "2016-09-01T02:05:14Z",
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


