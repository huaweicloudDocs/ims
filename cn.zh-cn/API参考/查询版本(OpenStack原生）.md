# 查询版本\(OpenStack原生）<a name="ZH-CN_TOPIC_0066978719"></a>

## 功能介绍<a name="section18441284152049"></a>

查询API版本信息。

## URI<a name="section21923693152049"></a>

URI格式

GET /

## 请求消息<a name="section62484847152049"></a>

请求样例

```
GET /
```

## 响应<a name="section47461859152049"></a>

-   参数列表

    <a name="table38630935152049"></a>
    <table><thead align="left"><tr id="row1849976152049"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.1"><p id="p15630386152049"><a name="p15630386152049"></a><a name="p15630386152049"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.2"><p id="p58101744152049"><a name="p58101744152049"></a><a name="p58101744152049"></a>类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.1.4.1.3"><p id="p27198362152049"><a name="p27198362152049"></a><a name="p27198362152049"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row55583702152049"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p5985974152049"><a name="p5985974152049"></a><a name="p5985974152049"></a>status</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p15101858152049"><a name="p15101858152049"></a><a name="p15101858152049"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p30612417152049"><a name="p30612417152049"></a><a name="p30612417152049"></a>接口状态</p>
    </td>
    </tr>
    <tr id="row7076302152049"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p36309602152049"><a name="p36309602152049"></a><a name="p36309602152049"></a>id</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p55396613152049"><a name="p55396613152049"></a><a name="p55396613152049"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p62685599152049"><a name="p62685599152049"></a><a name="p62685599152049"></a>接口ID</p>
    </td>
    </tr>
    <tr id="row27299481152049"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.1 "><p id="p63774346152049"><a name="p63774346152049"></a><a name="p63774346152049"></a>links</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.2 "><p id="p65448367152049"><a name="p65448367152049"></a><a name="p65448367152049"></a>List(Dict)</p>
    </td>
    <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.1.4.1.3 "><p id="p44225463152049"><a name="p44225463152049"></a><a name="p44225463152049"></a>自描述信息</p>
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
    "status": "CURRENT",
    "id": "v2.2",
    "links": [
    {
    "href": "https://image.az1.dc1.domainname.com/v2/",
    "rel": "self"
    }
    ]
    },
    {
    "status": "SUPPORTED",
    "id": "v2.1",
    "links": [
    {
    "href": "https://image.az1.dc1.domainname.com/v2/",
    "rel": "self"
    }
    ]
    },
    {
    "status": "SUPPORTED",
    "id": "v2.0",
    "links": [
    {
    "href": "https://image.az1.dc1.domainname.com/v2/",
    "rel": "self"
    }
    ]
    },
    {
    "status": "DEPRECATED",
    "id": "v1.1",
    "links": [
    {
    "href": "https://image.az1.dc1.domainname.com/v1/",
    "rel": "self"
    }
    ]
    },
    {
    "status": "DEPRECATED",
    "id": "v1.0",
    "links": [
    {
    "href": "https://image.az1.dc1.domainname.com/v1/",
    "rel": "self"
    }
    ]
    }
    ]
    }
    ```


## 错误码<a name="section37588986152049"></a>

不涉及。

