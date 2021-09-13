# 查询镜像支持的OS列表<a name="ims_03_0610"></a>

## 功能介绍<a name="section1194520316464"></a>

查询当前区域弹性云服务器的OS兼容性列表。

## 调试<a name="section44686511322"></a>

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?locale=zh-cn&consoleCurrentProductId=ims&consoleCurrentProductshort=&product=IMS&api=ListOsVersions)中调试该接口。

## URI<a name="section1594513117469"></a>

GET /v1/cloudimages/os\_version

**表 1**  查询参数

<a name="table1996117311464"></a>
<table><thead align="left"><tr id="row230533204615"><th class="cellrowborder" valign="top" width="15.101510151015102%" id="mcps1.2.5.1.1"><p id="p13051332144610"><a name="p13051332144610"></a><a name="p13051332144610"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="14.821482148214821%" id="mcps1.2.5.1.2"><p id="p1630520329462"><a name="p1630520329462"></a><a name="p1630520329462"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15.63156315631563%" id="mcps1.2.5.1.3"><p id="p5305332184616"><a name="p5305332184616"></a><a name="p5305332184616"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.445444544454446%" id="mcps1.2.5.1.4"><p id="p73056327467"><a name="p73056327467"></a><a name="p73056327467"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row430593218463"><td class="cellrowborder" valign="top" width="15.101510151015102%" headers="mcps1.2.5.1.1 "><p id="p330543210463"><a name="p330543210463"></a><a name="p330543210463"></a>tag</p>
</td>
<td class="cellrowborder" valign="top" width="14.821482148214821%" headers="mcps1.2.5.1.2 "><p id="p1630553264617"><a name="p1630553264617"></a><a name="p1630553264617"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15.63156315631563%" headers="mcps1.2.5.1.3 "><p id="p3305932144610"><a name="p3305932144610"></a><a name="p3305932144610"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.445444544454446%" headers="mcps1.2.5.1.4 "><p id="p1551018218225"><a name="p1551018218225"></a><a name="p1551018218225"></a>OS的标签。</p>
<p id="p182211042174911"><a name="p182211042174911"></a><a name="p182211042174911"></a>根据标签值可以过滤查询指定特性的OS信息。取值范围：</p>
<a name="ul16150991759"></a><a name="ul16150991759"></a><ul id="ul16150991759"><li>bms：表示该镜像支持BMS的os_version列表。</li><li>uefi：支持UEFI启动方式的os_version列表。</li><li>arm：显示基于arm架构的os_version列表。</li><li>x86：显示基于x86架构的os_version列表。</li></ul>
<p id="p16960182312504"><a name="p16960182312504"></a><a name="p16960182312504"></a>不带tag查询条件则默认查询当前region支持的所有的OS列表。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1394517316467"></a>

-   请求参数

    无

-   请求样例
    -   查询当前region支持的OS列表

        ```
        GET https://{Endpoint}/v1/cloudimages/os_version
        ```

    -   根据过滤条件查询OS列表

        ```
        GET https://{Endpoint}/v1/cloudimages/os_version?tag=kvm&tag=uefi
        ```



## 响应消息<a name="section639632154617"></a>

-   响应参数

    <a name="table18471105217552"></a>
    <table><thead align="left"><tr id="row14472175215519"><th class="cellrowborder" valign="top" width="27.352735273527358%" id="mcps1.1.4.1.1"><p id="p1420875716554"><a name="p1420875716554"></a><a name="p1420875716554"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="29.572957295729573%" id="mcps1.1.4.1.2"><p id="p5208175714558"><a name="p5208175714558"></a><a name="p5208175714558"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="43.074307430743076%" id="mcps1.1.4.1.3"><p id="p720812573554"><a name="p720812573554"></a><a name="p720812573554"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row114721752185519"><td class="cellrowborder" valign="top" width="27.352735273527358%" headers="mcps1.1.4.1.1 "><p id="p74721252205514"><a name="p74721252205514"></a><a name="p74721252205514"></a><em id="i975295211569"><a name="i975295211569"></a><a name="i975295211569"></a>[数组]</em></p>
    </td>
    <td class="cellrowborder" valign="top" width="29.572957295729573%" headers="mcps1.1.4.1.2 "><p id="p447219527557"><a name="p447219527557"></a><a name="p447219527557"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="43.074307430743076%" headers="mcps1.1.4.1.3 "><p id="p5472752155510"><a name="p5472752155510"></a><a name="p5472752155510"></a>详情请参见<a href="#table139163294618">表2</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2** _\[数组\]_字段说明

    <a name="table139163294618"></a>
    <table><thead align="left"><tr id="row103054322469"><th class="cellrowborder" valign="top" width="27.32%" id="mcps1.2.4.1.1"><p id="p43051732184618"><a name="p43051732184618"></a><a name="p43051732184618"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="29.9%" id="mcps1.2.4.1.2"><p id="p113051332184618"><a name="p113051332184618"></a><a name="p113051332184618"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="42.78%" id="mcps1.2.4.1.3"><p id="p23051732124619"><a name="p23051732124619"></a><a name="p23051732124619"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row83051832144620"><td class="cellrowborder" valign="top" width="27.32%" headers="mcps1.2.4.1.1 "><p id="p730511328463"><a name="p730511328463"></a><a name="p730511328463"></a>platform</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.9%" headers="mcps1.2.4.1.2 "><p id="p15305163211465"><a name="p15305163211465"></a><a name="p15305163211465"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.78%" headers="mcps1.2.4.1.3 "><p id="p130583216466"><a name="p130583216466"></a><a name="p130583216466"></a>操作系统平台。</p>
    </td>
    </tr>
    <tr id="row1978151914556"><td class="cellrowborder" valign="top" width="27.32%" headers="mcps1.2.4.1.1 "><p id="p878371917557"><a name="p878371917557"></a><a name="p878371917557"></a>version_list</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.9%" headers="mcps1.2.4.1.2 "><p id="p1978351917555"><a name="p1978351917555"></a><a name="p1978351917555"></a>Array of objects</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.78%" headers="mcps1.2.4.1.3 "><p id="p16783519185519"><a name="p16783519185519"></a><a name="p16783519185519"></a>返回的操作系统详情。</p>
    <p id="p679414231862"><a name="p679414231862"></a><a name="p679414231862"></a>具体请参见<a href="#table97141914183119">表3</a>。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 3** _\[数组\]_.version\_list字段数据结构说明

    <a name="table97141914183119"></a>
    <table><thead align="left"><tr id="row371491433115"><th class="cellrowborder" valign="top" width="27.52%" id="mcps1.2.4.1.1"><p id="p7714121416317"><a name="p7714121416317"></a><a name="p7714121416317"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="29.65%" id="mcps1.2.4.1.2"><p id="p1871471417315"><a name="p1871471417315"></a><a name="p1871471417315"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="42.83%" id="mcps1.2.4.1.3"><p id="p16714171416314"><a name="p16714171416314"></a><a name="p16714171416314"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row571511417314"><td class="cellrowborder" valign="top" width="27.52%" headers="mcps1.2.4.1.1 "><p id="p77431241133115"><a name="p77431241133115"></a><a name="p77431241133115"></a>platform</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.65%" headers="mcps1.2.4.1.2 "><p id="p671512144311"><a name="p671512144311"></a><a name="p671512144311"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.83%" headers="mcps1.2.4.1.3 "><p id="p4715171483115"><a name="p4715171483115"></a><a name="p4715171483115"></a>操作系统平台。</p>
    </td>
    </tr>
    <tr id="row7715161414314"><td class="cellrowborder" valign="top" width="27.52%" headers="mcps1.2.4.1.1 "><p id="p14541946123115"><a name="p14541946123115"></a><a name="p14541946123115"></a>os_version_key</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.65%" headers="mcps1.2.4.1.2 "><p id="p8715121423115"><a name="p8715121423115"></a><a name="p8715121423115"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.83%" headers="mcps1.2.4.1.3 "><p id="p197151314193110"><a name="p197151314193110"></a><a name="p197151314193110"></a>操作系统key值。</p>
    <p id="p330115135145"><a name="p330115135145"></a><a name="p330115135145"></a>默认取os_version的值为key值。</p>
    </td>
    </tr>
    <tr id="row19481135011317"><td class="cellrowborder" valign="top" width="27.52%" headers="mcps1.2.4.1.1 "><p id="p1848105013120"><a name="p1848105013120"></a><a name="p1848105013120"></a>os_version</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.65%" headers="mcps1.2.4.1.2 "><p id="p94821750163117"><a name="p94821750163117"></a><a name="p94821750163117"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.83%" headers="mcps1.2.4.1.3 "><p id="p548265033117"><a name="p548265033117"></a><a name="p548265033117"></a>操作系统完整信息。</p>
    </td>
    </tr>
    <tr id="row12801195211316"><td class="cellrowborder" valign="top" width="27.52%" headers="mcps1.2.4.1.1 "><p id="p16801152113116"><a name="p16801152113116"></a><a name="p16801152113116"></a>os_bit</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.65%" headers="mcps1.2.4.1.2 "><p id="p108011852183117"><a name="p108011852183117"></a><a name="p108011852183117"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.83%" headers="mcps1.2.4.1.3 "><p id="p118017521317"><a name="p118017521317"></a><a name="p118017521317"></a>操作系统的位数。</p>
    </td>
    </tr>
    <tr id="row946331133218"><td class="cellrowborder" valign="top" width="27.52%" headers="mcps1.2.4.1.1 "><p id="p34631215325"><a name="p34631215325"></a><a name="p34631215325"></a>os_type</p>
    </td>
    <td class="cellrowborder" valign="top" width="29.65%" headers="mcps1.2.4.1.2 "><p id="p1463161193211"><a name="p1463161193211"></a><a name="p1463161193211"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="42.83%" headers="mcps1.2.4.1.3 "><p id="p34639123211"><a name="p34639123211"></a><a name="p34639123211"></a>操作系统的类型。</p>
    </td>
    </tr>
    </tbody>
    </table>

-   响应样例

    ```
    STATUS CODE 200
    ```

    ```
    [
        {
            "platform": "SUSE",
            "version_list": [
                {
                    "platform": "SUSE",
                    "os_version_key": "SUSE Linux Enterprise Server 15 64bit",
                    "os_version": "SUSE Linux Enterprise Server 15 64bit",
                    "os_bit": 64,
                    "os_type": "Linux"
                },
                {
                    "platform": "SUSE",
                    "os_version_key": "SUSE Linux Enterprise Server 12 SP3 64bit",
                    "os_version": "SUSE Linux Enterprise Server 12 SP3 64bit",
                    "os_bit": 64,
                    "os_type": "Linux"
                }
            ]
        },
        {
            "platform": "Other",
            "version_list": [
                {
                    "platform": "Other",
                    "os_version_key": "Other(32 bit)",
                    "os_version": "Other(32 bit)",
                    "os_bit": 32,
                    "os_type": "Linux"
                }
            ]
        }
    ]
    ```


## 返回值<a name="section539103214611"></a>

-   正常

    200

-   异常

    <a name="table53911327463"></a>
    <table><thead align="left"><tr id="row11305143214468"><th class="cellrowborder" valign="top" width="46.46%" id="mcps1.1.3.1.1"><p id="p63051132164612"><a name="p63051132164612"></a><a name="p63051132164612"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.54%" id="mcps1.1.3.1.2"><p id="p133051932194617"><a name="p133051932194617"></a><a name="p133051932194617"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row11305133204615"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p13305143220466"><a name="p13305143220466"></a><a name="p13305143220466"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p17305203244617"><a name="p17305203244617"></a><a name="p17305203244617"></a>请求错误，具体返回错误码请参见<a href="错误码.md">错误码</a>。</p>
    </td>
    </tr>
    <tr id="row1130593211466"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p16305183274616"><a name="p16305183274616"></a><a name="p16305183274616"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p19305532164619"><a name="p19305532164619"></a><a name="p19305532164619"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row43051832104610"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p113057325469"><a name="p113057325469"></a><a name="p113057325469"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p12305153214469"><a name="p12305153214469"></a><a name="p12305153214469"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row23051532194620"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p1230553210462"><a name="p1230553210462"></a><a name="p1230553210462"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p9305432184614"><a name="p9305432184614"></a><a name="p9305432184614"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row1305132104618"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p183056324469"><a name="p183056324469"></a><a name="p183056324469"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p730533294620"><a name="p730533294620"></a><a name="p730533294620"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row1730513326464"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p6305153284615"><a name="p6305153284615"></a><a name="p6305153284615"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p6305133284616"><a name="p6305133284616"></a><a name="p6305133284616"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


