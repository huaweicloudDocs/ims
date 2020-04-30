# 查询镜像成员视图（OpenStack原生）<a name="ims_03_0717"></a>

## 功能介绍<a name="section4678164010456"></a>

该接口主要用于查询镜像成员视图，通过视图，用户可以了解到镜像成员包含哪些属性，同时也可以了解每个属性的数据类型。

## URI<a name="section1251307010456"></a>

GET /v2/schemas/member

## 请求消息<a name="section2411735110456"></a>

-   请求参数

    无

-   请求样例

    ```
    GET https://{Endpoint}/v2/schemas/member
    ```


## 响应消息<a name="section5835198610456"></a>

-   响应参数

    <a name="table5842318310456"></a>
    <table><thead align="left"><tr id="row6525201010456"><th class="cellrowborder" valign="top" width="24.407559244075593%" id="mcps1.1.4.1.1"><p id="p5092146210456"><a name="p5092146210456"></a><a name="p5092146210456"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="23.15768423157684%" id="mcps1.1.4.1.2"><p id="p2779017510456"><a name="p2779017510456"></a><a name="p2779017510456"></a>参数类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="52.434756524347556%" id="mcps1.1.4.1.3"><p id="p3641172510456"><a name="p3641172510456"></a><a name="p3641172510456"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row6366858710456"><td class="cellrowborder" valign="top" width="24.407559244075593%" headers="mcps1.1.4.1.1 "><p id="p5688188910456"><a name="p5688188910456"></a><a name="p5688188910456"></a>name</p>
    </td>
    <td class="cellrowborder" valign="top" width="23.15768423157684%" headers="mcps1.1.4.1.2 "><p id="p968421510456"><a name="p968421510456"></a><a name="p968421510456"></a>String</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p4622397510456"><a name="p4622397510456"></a><a name="p4622397510456"></a>视图名称。</p>
    </td>
    </tr>
    <tr id="row1336259710456"><td class="cellrowborder" valign="top" width="24.407559244075593%" headers="mcps1.1.4.1.1 "><p id="p862856110456"><a name="p862856110456"></a><a name="p862856110456"></a>properties</p>
    </td>
    <td class="cellrowborder" valign="top" width="23.15768423157684%" headers="mcps1.1.4.1.2 "><p id="p3921638110456"><a name="p3921638110456"></a><a name="p3921638110456"></a>Object</p>
    </td>
    <td class="cellrowborder" valign="top" width="52.434756524347556%" headers="mcps1.1.4.1.3 "><p id="p1622165310562"><a name="p1622165310562"></a><a name="p1622165310562"></a>镜像属性说明，主要是对基础属性的说明，包含每个属性的取值类型，用途。</p>
    <p id="p4120204111445"><a name="p4120204111445"></a><a name="p4120204111445"></a>具体参数说明可参考<a href="镜像属性.md">镜像属性</a>。</p>
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
        "name": "member",
        "properties": {
            "status": {
                "enum": [
                    "pending",
                    "accepted",
                    "rejected"
                ],
                "type": "string",
                "description": "The status of this image member"
            },
            "created_at": {
                "type": "string",
                "description": "Date and time of image member creation"
            },
            "updated_at": {
                "type": "string",
                "description": "Date and time of last modification of image member"
            },
            "image_id": {
                "pattern": "^([0-9a-fA-F]){8}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){4}-([0-9a-fA-F]){12}$",
                "type": "string",
                "description": "An identifier for the image"
            },
            "member_id": {
                "type": "string",
                "description": "An identifier for the image member (tenantId)"
            },
            "schema": {
                "readOnly": true,
                "type": "string"
            }
        }
    }
    ```


## 返回值<a name="section3184290310456"></a>

-   正常

    200

-   异常

    <a name="table5046465910456"></a>
    <table><thead align="left"><tr id="row5279442910456"><th class="cellrowborder" valign="top" width="46.46%" id="mcps1.1.3.1.1"><p id="p4849034810456"><a name="p4849034810456"></a><a name="p4849034810456"></a>返回值</p>
    </th>
    <th class="cellrowborder" valign="top" width="53.54%" id="mcps1.1.3.1.2"><p id="p3540414010456"><a name="p3540414010456"></a><a name="p3540414010456"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row4916310910456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p2278886210456"><a name="p2278886210456"></a><a name="p2278886210456"></a>400 Bad Request</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p3395849510456"><a name="p3395849510456"></a><a name="p3395849510456"></a>请求错误。</p>
    </td>
    </tr>
    <tr id="row3719100210456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p5968121110456"><a name="p5968121110456"></a><a name="p5968121110456"></a>401 Unauthorized</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p233996110456"><a name="p233996110456"></a><a name="p233996110456"></a>鉴权失败。</p>
    </td>
    </tr>
    <tr id="row2105965410456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p2811042610456"><a name="p2811042610456"></a><a name="p2811042610456"></a>403 Forbidden</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p6235199710456"><a name="p6235199710456"></a><a name="p6235199710456"></a>没有操作权限。</p>
    </td>
    </tr>
    <tr id="row2429706910456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p2190558110456"><a name="p2190558110456"></a><a name="p2190558110456"></a>404 Not Found</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p2952161710456"><a name="p2952161710456"></a><a name="p2952161710456"></a>找不到资源。</p>
    </td>
    </tr>
    <tr id="row6436796410456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p4642261010456"><a name="p4642261010456"></a><a name="p4642261010456"></a>500 Internal Server Error</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p213507210456"><a name="p213507210456"></a><a name="p213507210456"></a>服务内部错误。</p>
    </td>
    </tr>
    <tr id="row1921565610456"><td class="cellrowborder" valign="top" width="46.46%" headers="mcps1.1.3.1.1 "><p id="p1296433510456"><a name="p1296433510456"></a><a name="p1296433510456"></a>503 Service Unavailable</p>
    </td>
    <td class="cellrowborder" valign="top" width="53.54%" headers="mcps1.1.3.1.2 "><p id="p4347817710456"><a name="p4347817710456"></a><a name="p4347817710456"></a>服务不可用。</p>
    </td>
    </tr>
    </tbody>
    </table>


