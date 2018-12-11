# 查询镜像元数据（OpenStack原生v1--已废弃，不推荐使用）<a name="ZH-CN_TOPIC_0066978721"></a>

## 功能介绍<a name="section6658307515228"></a>

查询镜像元数据。

当前接口已废弃，推荐使用[查询镜像详情（OpenStack原生）](查询镜像详情（OpenStack原生）.md)。

## URI<a name="section1935356215228"></a>

URI格式

HEAD /v1/images/\{image\_id\}

## 请求消息<a name="section6467246815228"></a>

请求样例

```
HEAD /v1/images/3c3d1d01-b48a-4639-8a88-08be3b9b5d78
```

## 响应<a name="section1674295515228"></a>

-   参数说明

    <a name="table1400212915228"></a>
    <table><thead align="left"><tr id="row5823351215228"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p1929404715228"><a name="p1929404715228"></a><a name="p1929404715228"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p1931400315228"><a name="p1931400315228"></a><a name="p1931400315228"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p1764174415228"><a name="p1764174415228"></a><a name="p1764174415228"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1969514515228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p5180291115228"><a name="p5180291115228"></a><a name="p5180291115228"></a>Status</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p3528623315228"><a name="p3528623315228"></a><a name="p3528623315228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5450463515228"><a name="p5450463515228"></a><a name="p5450463515228"></a>镜像状态</p>
    </td>
    </tr>
    <tr id="row2077966715228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p543149615228"><a name="p543149615228"></a><a name="p543149615228"></a>Virtual_size</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p3729805415228"><a name="p3729805415228"></a><a name="p3729805415228"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p3361529015228"><a name="p3361529015228"></a><a name="p3361529015228"></a>镜像虚拟大小</p>
    </td>
    </tr>
    <tr id="row3410215815228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1081140415228"><a name="p1081140415228"></a><a name="p1081140415228"></a>Name</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p330853515228"><a name="p330853515228"></a><a name="p330853515228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p3113630615228"><a name="p3113630615228"></a><a name="p3113630615228"></a>镜像名称</p>
    </td>
    </tr>
    <tr id="row1179129815228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1557104315228"><a name="p1557104315228"></a><a name="p1557104315228"></a>Deleted</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p5329496515228"><a name="p5329496515228"></a><a name="p5329496515228"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p3108609015228"><a name="p3108609015228"></a><a name="p3108609015228"></a>镜像是否已删除</p>
    </td>
    </tr>
    <tr id="row1133935915228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p4607291015228"><a name="p4607291015228"></a><a name="p4607291015228"></a>Container_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p4091822515228"><a name="p4091822515228"></a><a name="p4091822515228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p2902213315228"><a name="p2902213315228"></a><a name="p2902213315228"></a>镜像容器类型</p>
    </td>
    </tr>
    <tr id="row5987260815228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1784309415228"><a name="p1784309415228"></a><a name="p1784309415228"></a>Created_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p3600451615228"><a name="p3600451615228"></a><a name="p3600451615228"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p243466715228"><a name="p243466715228"></a><a name="p243466715228"></a>镜像创建时间</p>
    </td>
    </tr>
    <tr id="row2191200515228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p3004199615228"><a name="p3004199615228"></a><a name="p3004199615228"></a>Disk_format</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1748264015228"><a name="p1748264015228"></a><a name="p1748264015228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1455575715228"><a name="p1455575715228"></a><a name="p1455575715228"></a>镜像文件类型</p>
    </td>
    </tr>
    <tr id="row6389295115228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p794657015228"><a name="p794657015228"></a><a name="p794657015228"></a>Updated_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p3969241315228"><a name="p3969241315228"></a><a name="p3969241315228"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p3953030815228"><a name="p3953030815228"></a><a name="p3953030815228"></a>镜像更新时间</p>
    </td>
    </tr>
    <tr id="row2022845615228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2789220715228"><a name="p2789220715228"></a><a name="p2789220715228"></a>Property</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p4467631515228"><a name="p4467631515228"></a><a name="p4467631515228"></a>Dict</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5689958515228"><a name="p5689958515228"></a><a name="p5689958515228"></a>镜像属性</p>
    </td>
    </tr>
    <tr id="row4233422315228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p652003815228"><a name="p652003815228"></a><a name="p652003815228"></a>Owner</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p5836106115228"><a name="p5836106115228"></a><a name="p5836106115228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5085734215228"><a name="p5085734215228"></a><a name="p5085734215228"></a>镜像所属租户</p>
    </td>
    </tr>
    <tr id="row5506289515228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p3090947115228"><a name="p3090947115228"></a><a name="p3090947115228"></a>Protected</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p2063919515228"><a name="p2063919515228"></a><a name="p2063919515228"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p5518505015228"><a name="p5518505015228"></a><a name="p5518505015228"></a>镜像是否受保护</p>
    </td>
    </tr>
    <tr id="row2690340715228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p3169237115228"><a name="p3169237115228"></a><a name="p3169237115228"></a>Min_ram</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1694522215228"><a name="p1694522215228"></a><a name="p1694522215228"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p4532902415228"><a name="p4532902415228"></a><a name="p4532902415228"></a>运行镜像所需最小内存，单位MB</p>
    </td>
    </tr>
    <tr id="row530803415228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2729760315228"><a name="p2729760315228"></a><a name="p2729760315228"></a>Checksum</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p6362220015228"><a name="p6362220015228"></a><a name="p6362220015228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p812156815228"><a name="p812156815228"></a><a name="p812156815228"></a>镜像校验和，上传镜像文件后存在</p>
    </td>
    </tr>
    <tr id="row598524815228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p1504306415228"><a name="p1504306415228"></a><a name="p1504306415228"></a>Min_disk</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1052864815228"><a name="p1052864815228"></a><a name="p1052864815228"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p2344248215228"><a name="p2344248215228"></a><a name="p2344248215228"></a>运行镜像所需最小磁盘，单位GB</p>
    </td>
    </tr>
    <tr id="row965575415228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p4391859515228"><a name="p4391859515228"></a><a name="p4391859515228"></a>Is_public</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p63644115228"><a name="p63644115228"></a><a name="p63644115228"></a>Bool</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1494066515228"><a name="p1494066515228"></a><a name="p1494066515228"></a>是否为公共镜像</p>
    </td>
    </tr>
    <tr id="row24826515228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p2010950115228"><a name="p2010950115228"></a><a name="p2010950115228"></a>Deleted_at</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p1825691415228"><a name="p1825691415228"></a><a name="p1825691415228"></a>Datetime</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p6140441415228"><a name="p6140441415228"></a><a name="p6140441415228"></a>镜像删除时间</p>
    </td>
    </tr>
    <tr id="row1576881415228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p220557615228"><a name="p220557615228"></a><a name="p220557615228"></a>Id</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p4443395815228"><a name="p4443395815228"></a><a name="p4443395815228"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p1029672015228"><a name="p1029672015228"></a><a name="p1029672015228"></a>镜像UUID</p>
    </td>
    </tr>
    <tr id="row2556161915228"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p5722522815228"><a name="p5722522815228"></a><a name="p5722522815228"></a>Size</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p473185315228"><a name="p473185315228"></a><a name="p473185315228"></a>Int</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p4139514515228"><a name="p4139514515228"></a><a name="p4139514515228"></a>镜像大小，上传镜像文件后存在</p>
    </td>
    </tr>
    </tbody>
    </table>

    上述响应参数在HTTP响应消息的header中返回。

-   响应样例

    ```
    HTTP/1.1 200 OK
    ```

    ```
    Content-Type: text/html; charset=UTF-8
    Content-Length: 0
    X-Image-Meta-Id: 3c3d1d01-b48a-4639-8a88-08be3b9b5d78
    X-Image-Meta-Deleted: False
    X-Image-Meta-Container_format: bare
    X-Image-Meta-Checksum: 64d7c1cd2b6f60c92c14662941cb7913
    X-Image-Meta-Protected: False
    X-Image-Meta-Min_disk: 0
    X-Image-Meta-Created_at: 2016-05-22T06:04:20.425843
    X-Image-Meta-Size: 13167616
    X-Image-Meta-Status: active
    X-Image-Meta-Is_public: True
    X-Image-Meta-Min_ram: 0
    X-Image-Meta-Owner: 23f4cb75768d4febb39542ef6fe169f3
    X-Image-Meta-Updated_at: 2016-05-22T06:04:22.719791
    X-Image-Meta-Disk_format: qcow2
    X-Image-Meta-Name: cirros
    Etag: 64d7c1cd2b6f60c92c14662941cb7913
    X-Openstack-Request-Id: req-7123ca83-da23-4f4e-9ed6-accd3707d333
    Date: Mon, 23 May 2016 02:29:54 GMT
    ```


## 错误码<a name="section6571722315228"></a>

<a name="table2149488115228"></a>
<table><thead align="left"><tr id="row2133235215228"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p5019893415228"><a name="p5019893415228"></a><a name="p5019893415228"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p3958189015228"><a name="p3958189015228"></a><a name="p3958189015228"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row5201648915228"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p5258610115228"><a name="p5258610115228"></a><a name="p5258610115228"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p3161582215228"><a name="p3161582215228"></a><a name="p3161582215228"></a>Not Found</p>
<p id="p1610694715228"><a name="p1610694715228"></a><a name="p1610694715228"></a>该错误一般是由于指定的镜像不存在。</p>
</td>
</tr>
</tbody>
</table>

