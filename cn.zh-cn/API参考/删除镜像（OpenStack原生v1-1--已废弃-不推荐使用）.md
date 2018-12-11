# 删除镜像（OpenStack原生v1.1--已废弃，不推荐使用）<a name="ZH-CN_TOPIC_0066978722"></a>

## 功能介绍<a name="section65883044152228"></a>

删除镜像，软删除指定ID的镜像，镜像在库中依然保存，只将该镜像的status状态置为deleted。

当前接口已废弃，推荐使用[删除镜像（OpenStack原生）](删除镜像（OpenStack原生）.md)。

## URI<a name="section45901761152228"></a>

URI格式

DELETE /v1.1/images/\{image\_id\}

## 请求消息<a name="section59210700152228"></a>

请求样例

```
DELETE /v1.1/images/3c3d1d01-b48a-4639-8a88-08be3b9b5d78
```

## 响应参数<a name="section13601000152228"></a>

响应样例

```
HTTP/1.1 200 OK
```

```
Content-Type: text/html; charset=UTF-8
Content-Length: 0
X-Openstack-Request-Id: req-75e9edca-7b43-47da-bdc5-d39be469b72f
Date: Mon, 23 May 2016 02:43:34 GMT
```

## 错误码<a name="section47464039152228"></a>

<a name="table19381959152228"></a>
<table><thead align="left"><tr id="row10745212152228"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="p65055850152228"><a name="p65055850152228"></a><a name="p65055850152228"></a>错误码</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="p35032537152228"><a name="p35032537152228"></a><a name="p35032537152228"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row19063281152228"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="p621913152228"><a name="p621913152228"></a><a name="p621913152228"></a>404</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="p50374969152228"><a name="p50374969152228"></a><a name="p50374969152228"></a>Not Found</p>
<p id="p50721542152228"><a name="p50721542152228"></a><a name="p50721542152228"></a>该错误一般是由于指定的镜像不存在。</p>
</td>
</tr>
</tbody>
</table>

