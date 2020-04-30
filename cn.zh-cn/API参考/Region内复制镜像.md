# Region内复制镜像<a name="ims_03_0627"></a>

## 功能介绍<a name="section57853128105524"></a>

该接口为扩展接口，主要用于用户将一个已有镜像复制为另一个镜像。复制镜像时，可以更改镜像的加密等属性，以满足不同的场景。

该接口为异步接口，返回job\_id说明任务下发成功，查询异步任务状态，如果是success说明任务执行成功，如果是failed说明任务执行失败。如何查询异步任务，请参见[异步任务查询](异步任务查询.md)。

## 约束与限制<a name="section183915210102"></a>

支持用户复制“正常”状态的私有镜像。

整机镜像不支持区域内复制。

使用ISO文件创建的私有镜像不支持区域内复制。

## URI<a name="section30564347105524"></a>

POST /v1/cloudimages/\{image\_id\}/copy

参数说明请参见[表1](#table51065259105524)。

**表 1**  参数说明

<a name="table51065259105524"></a>
<table><thead align="left"><tr id="row36742558105524"><th class="cellrowborder" valign="top" width="19.388061193880613%" id="mcps1.2.5.1.1"><p id="p23357191105524"><a name="p23357191105524"></a><a name="p23357191105524"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="18.80811918808119%" id="mcps1.2.5.1.2"><p id="p12884280105524"><a name="p12884280105524"></a><a name="p12884280105524"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="18.488151184881513%" id="mcps1.2.5.1.3"><p id="p36993754105524"><a name="p36993754105524"></a><a name="p36993754105524"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="43.31566843315669%" id="mcps1.2.5.1.4"><p id="p43704084105524"><a name="p43704084105524"></a><a name="p43704084105524"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row50369935105524"><td class="cellrowborder" valign="top" width="19.388061193880613%" headers="mcps1.2.5.1.1 "><p id="p53432947105524"><a name="p53432947105524"></a><a name="p53432947105524"></a>image_id</p>
</td>
<td class="cellrowborder" valign="top" width="18.80811918808119%" headers="mcps1.2.5.1.2 "><p id="p33101414105524"><a name="p33101414105524"></a><a name="p33101414105524"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="18.488151184881513%" headers="mcps1.2.5.1.3 "><p id="p63968915105524"><a name="p63968915105524"></a><a name="p63968915105524"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="43.31566843315669%" headers="mcps1.2.5.1.4 "><p id="p14099616105524"><a name="p14099616105524"></a><a name="p14099616105524"></a>镜像ID。</p>
<p id="p127065072116"><a name="p127065072116"></a><a name="p127065072116"></a>如何获取镜像ID，请参见<a href="查询镜像列表.md">查询镜像列表</a>。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section1218229105524"></a>

-   请求参数

    <a name="table6850073105524"></a>
    <table><thead align="left"><tr id="row3268825105524"><th class="cellrowborder" valign="top" width="19.541954195419542%" id="mcps1.1.5.1.1"><p id="p63448301105524"><a name="p63448301105524"></a><a name="p63448301105524"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.72177217721772%" id="mcps1.1.5.1.2"><p id="p39038757105524"><a name="p39038757105524"></a><a name="p39038757105524"></a>是否必选</p>
    </th>
    <th class="cellrowborder" valign="top" width="17.42174217421742%" id="mcps1.1.5.1.3"><p id="p8022762105524"><a name="p8022762105524"></a><a name="p8022762105524"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="45.314531453145314%" id="mcps1.1.5.1.4"><p id="p45863971105524"><a name="p45863971105524"></a><a name="p45863971105524"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row23994169105524"><td class="cellrowborder" valign="top" width="19.541954195419542%" headers="mcps1.1.5.1.1 "><p id="p64479507105524"><a name="p64479507105524"></a><a name="p64479507105524"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.72177217721772%" headers="mcps1.1.5.1.2 "><p id="p55457561105524"><a name="p55457561105524"></a><a name="p55457561105524"></a>是</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.42174217421742%" headers="mcps1.1.5.1.3 "><p id="p62877493105524"><a name="p62877493105524"></a><a name="p62877493105524"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.314531453145314%" headers="mcps1.1.5.1.4 "><p id="p34441981163338"><a name="p34441981163338"></a><a name="p34441981163338"></a>镜像名称。name参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。</p>
    </td>
    </tr>
    <tr id="row2338354105524"><td class="cellrowborder" valign="top" width="19.541954195419542%" headers="mcps1.1.5.1.1 "><p id="p55189008105524"><a name="p55189008105524"></a><a name="p55189008105524"></a>description</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.72177217721772%" headers="mcps1.1.5.1.2 "><p id="p41124638105524"><a name="p41124638105524"></a><a name="p41124638105524"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.42174217421742%" headers="mcps1.1.5.1.3 "><p id="p42761348105524"><a name="p42761348105524"></a><a name="p42761348105524"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.314531453145314%" headers="mcps1.1.5.1.4 "><p id="p30451415163338"><a name="p30451415163338"></a><a name="p30451415163338"></a>镜像描述信息。_description参数说明请参考<a href="镜像属性.md#section61598810155254">镜像属性</a>。支持字母、数字、中文等，不支持回车、&lt;、&gt;，长度不能超过1024个字符。默认为空。</p>
    </td>
    </tr>
    <tr id="row34510150105524"><td class="cellrowborder" valign="top" width="19.541954195419542%" headers="mcps1.1.5.1.1 "><p id="p43858769105524"><a name="p43858769105524"></a><a name="p43858769105524"></a>cmk_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.72177217721772%" headers="mcps1.1.5.1.2 "><p id="p62899376105524"><a name="p62899376105524"></a><a name="p62899376105524"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.42174217421742%" headers="mcps1.1.5.1.3 "><p id="p61684684105524"><a name="p61684684105524"></a><a name="p61684684105524"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.314531453145314%" headers="mcps1.1.5.1.4 "><p id="p30403468105524"><a name="p30403468105524"></a><a name="p30403468105524"></a>加密密钥。默认为空。</p>
    </td>
    </tr>
    <tr id="row25391820153217"><td class="cellrowborder" valign="top" width="19.541954195419542%" headers="mcps1.1.5.1.1 "><p id="p1930422213328"><a name="p1930422213328"></a><a name="p1930422213328"></a>enterprise_project_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.72177217721772%" headers="mcps1.1.5.1.2 "><p id="p143046221323"><a name="p143046221323"></a><a name="p143046221323"></a>否</p>
    </td>
    <td class="cellrowborder" valign="top" width="17.42174217421742%" headers="mcps1.1.5.1.3 "><p id="p9304202215329"><a name="p9304202215329"></a><a name="p9304202215329"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="45.314531453145314%" headers="mcps1.1.5.1.4 "><p id="p10305182217584"><a name="p10305182217584"></a><a name="p10305182217584"></a>表示当前镜像所属的企业项目。</p>
    <a name="ul444316189359"></a><a name="ul444316189359"></a><ul id="ul444316189359"><li>取值为0或无该值，表示属于default企业项目。</li><li>取值为UUID，表示属于该UUID对应的企业项目。<p id="ims_03_0605_p14686203192413"><a name="ims_03_0605_p14686203192413"></a><a name="ims_03_0605_p14686203192413"></a>关于企业项目ID的获取及企业项目特性的详细信息，请参考“<a href="https://support.huaweicloud.com/usermanual-em/zh-cn_topic_0123692049.html" target="_blank" rel="noopener noreferrer">企业中心总览</a>”。</p>
    </li></ul>
    </td>
    </tr>
    </tbody>
    </table>


-   请求样例

    ```
    POST https://{Endpoint}/v1/cloudimages/465076de-dc36-4aec-80f5-ef9d8009428f/copy
    ```

    ```
    {
        "name": "ims_encrypted_copy3",
        "description": "test copy",
        "cmk_id": "bd66288c-9081-460a-8227-4cbd0c814cb4"
    }
    ```


## 响应消息<a name="section32485736105524"></a>

-   响应参数

    <a name="table1162152105524"></a>
    <table><thead align="left"><tr id="row45730117105524"><th class="cellrowborder" valign="top" width="23.11768823117688%" id="mcps1.1.4.1.1"><p id="p13151974105524"><a name="p13151974105524"></a><a name="p13151974105524"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="24.447555244475552%" id="mcps1.1.4.1.2"><p id="p55216927105524"><a name="p55216927105524"></a><a name="p55216927105524"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="52.434756524347556%" id="mcps1.1.4.1.3"><p id="p43386118105524"><a name="p43386118105524"></a><a name="p43386118105524"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row24614698105524"><td class="cellrowborder" valign="top" width="23.11768823117688%" headers="mcps1.1.4.1.1 "><p id="p47633522105524"><a name="p47633522105524"></a><a name="p47633522105524"></a>job_id</p>
    </td>
    <td class="cellrowborder" valign="top" width="24.447555244475552%" headers="mcps1.1.4.1.2 "><p id="p64671376105524"><a name="p64671376105524"></a><a name="p64671376105524"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p3890102105524"><a name="p3890102105524"></a><a name="p3890102105524"></a>异步任务ID。</p>
    <p id="p19968122117312"><a name="p19968122117312"></a><a name="p19968122117312"></a>详情请参见<a href="异步任务查询.md">异步任务查询</a>。</p>
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
        "job_id": "edc89b490d7d4392898e19b2deb34797"
    }
    ```


## 返回值<a name="section40084941"></a>

-   正常

    200

-   异常

    <a name="table1069408417333"></a>
    <table><thead align="left"><tr id="row4772021317333"><th class="cellrowborder" valign="top" width="46.54%" id="mcps1.1.3.1.1"><p id="p4013206717333"><a name="p4013206717333"></a><a name="p4013206717333"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.459999999999994%" id="mcps1.1.3.1.2"><p id="p2947196917333"><a name="p2947196917333"></a><a name="p2947196917333"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3841925517333"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p2495195017333"><a name="p2495195017333"></a><a name="p2495195017333"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p784206117333"><a name="p784206117333"></a><a name="p784206117333"></a>请求错误，具体返回错误码请参<a href="错误码.md">错误码</a>。</p>
    </td>
    </tr>
    <tr id="row3122722917333"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4637763817333"><a name="p4637763817333"></a><a name="p4637763817333"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p6560116717333"><a name="p6560116717333"></a><a name="p6560116717333"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row5353959117333"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4173958717333"><a name="p4173958717333"></a><a name="p4173958717333"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p2546341217333"><a name="p2546341217333"></a><a name="p2546341217333"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row5197513192250"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p21898657192252"><a name="p21898657192252"></a><a name="p21898657192252"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p28960832192252"><a name="p28960832192252"></a><a name="p28960832192252"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row2784412417333"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4078159117333"><a name="p4078159117333"></a><a name="p4078159117333"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p1497458717333"><a name="p1497458717333"></a><a name="p1497458717333"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row55355517333"><td class="cellrowborder" valign="top" width="46.54%" headers="mcps1.1.3.1.1 "><p id="p4483799017333"><a name="p4483799017333"></a><a name="p4483799017333"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.459999999999994%" headers="mcps1.1.3.1.2 "><p id="p799858217333"><a name="p799858217333"></a><a name="p799858217333"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


