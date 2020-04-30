# 更新镜像成员状态（OpenStack原生）<a name="ims_03_0721"></a>

## 功能介绍<a name="section39958021"></a>

用户接受或者拒绝共享镜像时，使用该接口更新镜像成员的状态。

## URI<a name="section24077873"></a>

PUT /v2/images/\{image\_id\}/members/\{member\_id\}

参数说明请参见[表1](#table37590215162351)。

**表 1**  参数说明

<a name="table37590215162351"></a>
<table><thead align="left"><tr id="row14906674162351"><th class="cellrowborder" valign="top" width="23.347665233476654%" id="mcps1.2.5.1.1"><p id="p66589937162351"><a name="p66589937162351"></a><a name="p66589937162351"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20.73792620737926%" id="mcps1.2.5.1.2"><p id="p25075841162351"><a name="p25075841162351"></a><a name="p25075841162351"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="21.587841215878413%" id="mcps1.2.5.1.3"><p id="p3182134421246"><a name="p3182134421246"></a><a name="p3182134421246"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="34.32656734326567%" id="mcps1.2.5.1.4"><p id="p17877258162351"><a name="p17877258162351"></a><a name="p17877258162351"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row38771763162351"><td class="cellrowborder" valign="top" width="23.347665233476654%" headers="mcps1.2.5.1.1 "><p id="p944143142612"><a name="p944143142612"></a><a name="p944143142612"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="20.73792620737926%" headers="mcps1.2.5.1.2 "><p id="p9366762142612"><a name="p9366762142612"></a><a name="p9366762142612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.587841215878413%" headers="mcps1.2.5.1.3 "><p id="p20510233142612"><a name="p20510233142612"></a><a name="p20510233142612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="34.32656734326567%" headers="mcps1.2.5.1.4 "><p id="p50716165142612"><a name="p50716165142612"></a><a name="p50716165142612"></a>镜像ID</p>
</td>
</tr>
<tr id="row5130782114260"><td class="cellrowborder" valign="top" width="23.347665233476654%" headers="mcps1.2.5.1.1 "><p id="p62209086142612"><a name="p62209086142612"></a><a name="p62209086142612"></a>member_id</p>
</td>
<td class="cellrowborder" valign="top" width="20.73792620737926%" headers="mcps1.2.5.1.2 "><p id="p5771200142612"><a name="p5771200142612"></a><a name="p5771200142612"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="21.587841215878413%" headers="mcps1.2.5.1.3 "><p id="p64814042142612"><a name="p64814042142612"></a><a name="p64814042142612"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="34.32656734326567%" headers="mcps1.2.5.1.4 "><p id="p15446069142612"><a name="p15446069142612"></a><a name="p15446069142612"></a>成员ID</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section15374270"></a>

-   请求参数

    <a name="table31018281142633"></a>
    <table><thead align="left"><tr id="row35509333142633"><th class="cellrowborder" valign="top" width="17.03%" id="mcps1.1.5.1.1"><p id="p57683706142633"><a name="p57683706142633"></a><a name="p57683706142633"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.990000000000002%" id="mcps1.1.5.1.2"><p id="p41868624142633"><a name="p41868624142633"></a><a name="p41868624142633"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.52%" id="mcps1.1.5.1.3"><p id="p35915390142633"><a name="p35915390142633"></a><a name="p35915390142633"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="47.46%" id="mcps1.1.5.1.4"><p id="p23465517142633"><a name="p23465517142633"></a><a name="p23465517142633"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row21658757142633"><td class="cellrowborder" valign="top" width="17.03%" headers="mcps1.1.5.1.1 "><p id="p9528877142633"><a name="p9528877142633"></a><a name="p9528877142633"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.990000000000002%" headers="mcps1.1.5.1.2 "><p id="p33641549142633"><a name="p33641549142633"></a><a name="p33641549142633"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.52%" headers="mcps1.1.5.1.3 "><p id="p40610958142633"><a name="p40610958142633"></a><a name="p40610958142633"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.46%" headers="mcps1.1.5.1.4 "><p id="p461165194819"><a name="p461165194819"></a><a name="p461165194819"></a>镜像成员的状态。</p>
    <p id="p166859539539"><a name="p166859539539"></a><a name="p166859539539"></a>取值如下：</p>
    <a name="ul346242429557"></a><a name="ul346242429557"></a><ul id="ul346242429557"><li>accepted：表示接受共享镜像。接受后，该镜像在用户镜像列表中可见，用户可以使用该镜像创建<span id="text1013631371215"><a name="text1013631371215"></a><a name="text1013631371215"></a>云服务器</span><span id="text20797319151218"><a name="text20797319151218"></a><a name="text20797319151218"></a></span>。</li><li>rejected：表示拒绝共享镜像。拒绝后，该镜像在用户镜像列表中不可见，但是，用户仍然可以使用该镜像创建<span id="text1028103661311"><a name="text1028103661311"></a><a name="text1028103661311"></a>云服务器</span><span id="text82811536111310"><a name="text82811536111310"></a><a name="text82811536111310"></a></span>。</li></ul>
    </td>
    </tr>
    <tr id="row26011552202513"><td class="cellrowborder" valign="top" width="17.03%" headers="mcps1.1.5.1.1 "><p id="p1560120527251"><a name="p1560120527251"></a><a name="p1560120527251"></a>vault_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.990000000000002%" headers="mcps1.1.5.1.2 "><p id="p26016529259"><a name="p26016529259"></a><a name="p26016529259"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.52%" headers="mcps1.1.5.1.3 "><p id="p1460105282515"><a name="p1460105282515"></a><a name="p1460105282515"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="47.46%" headers="mcps1.1.5.1.4 "><p id="p49862274296"><a name="p49862274296"></a><a name="p49862274296"></a>存储库ID。</p>
    <p id="p12601125211251"><a name="p12601125211251"></a><a name="p12601125211251"></a>如果是CBR创建的整机镜像，则在接受该共享镜像时，为必选参数，需传入该值。</p>
    <p id="p116364254172"><a name="p116364254172"></a><a name="p116364254172"></a>存储库ID可以从云备份服务控制台获取，或者参考“<a href="https://support.huaweicloud.com/api-cbr/ListVault.html" target="_blank" rel="noopener noreferrer">查询存储库列表</a>”查询。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   请求样例
    -   镜像为非整机镜像时

        ```
        PUT https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
        ```

        ```
        {
            "status":"accepted"
        }
        ```

    -   镜像为整机镜像时

        ```
        PUT https://{Endpoint}/v2/images/d164b5df-1bc3-4c3f-893e-3e471fd16e64/members/edc89b490d7d4392898e19b2deb34797
        ```

        ```
        {
            "status":"accepted",
            "vault_id":"6yhtb5df-1bc3-4c3f-893e-3e4716yhgt61"
        }
        ```



## 响应消息<a name="section4150710"></a>

-   响应参数

    <a name="table3940930519484"></a>
    <table><thead align="left"><tr id="row5108650619484"><th class="cellrowborder" valign="top" width="27.389999999999997%" id="mcps1.1.4.1.1"><p id="p4436630719484"><a name="p4436630719484"></a><a name="p4436630719484"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="24.42%" id="mcps1.1.4.1.2"><p id="p3690111319484"><a name="p3690111319484"></a><a name="p3690111319484"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="48.19%" id="mcps1.1.4.1.3"><p id="p3620014719484"><a name="p3620014719484"></a><a name="p3620014719484"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row4653077719484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p1237238714338"><a name="p1237238714338"></a><a name="p1237238714338"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p4061628614338"><a name="p4061628614338"></a><a name="p4061628614338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p158487614338"><a name="p158487614338"></a><a name="p158487614338"></a>共享状态</p>
    </td>
    </tr>
    <tr id="row6237230419484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p1452463514338"><a name="p1452463514338"></a><a name="p1452463514338"></a>created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p154357214338"><a name="p154357214338"></a><a name="p154357214338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p5792053614338"><a name="p5792053614338"></a><a name="p5792053614338"></a>共享时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row5992935019484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p1259565314338"><a name="p1259565314338"></a><a name="p1259565314338"></a>updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p2907381014338"><a name="p2907381014338"></a><a name="p2907381014338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p616838914338"><a name="p616838914338"></a><a name="p616838914338"></a>更新时间，格式为UTC时间</p>
    </td>
    </tr>
    <tr id="row1403543619484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p46179614338"><a name="p46179614338"></a><a name="p46179614338"></a>image_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p995083914338"><a name="p995083914338"></a><a name="p995083914338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p71165114338"><a name="p71165114338"></a><a name="p71165114338"></a>镜像ID</p>
    </td>
    </tr>
    <tr id="row4544843919484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p4903219314338"><a name="p4903219314338"></a><a name="p4903219314338"></a>member_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p4743364614338"><a name="p4743364614338"></a><a name="p4743364614338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p1692010914338"><a name="p1692010914338"></a><a name="p1692010914338"></a>成员ID</p>
    </td>
    </tr>
    <tr id="row4954506419484"><td class="cellrowborder" valign="top" width="27.389999999999997%" headers="mcps1.1.4.1.1 "><p id="p5383793114338"><a name="p5383793114338"></a><a name="p5383793114338"></a>schema</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.42%" headers="mcps1.1.4.1.2 "><p id="p3671632714338"><a name="p3671632714338"></a><a name="p3671632714338"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="48.19%" headers="mcps1.1.4.1.3 "><p id="p2123248314338"><a name="p2123248314338"></a><a name="p2123248314338"></a>共享视图</p>
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


