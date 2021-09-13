# 安装Windows特殊驱动<a name="ims_01_0404"></a>

## 操作场景<a name="section273431714186"></a>

对于一些类型的弹性云服务器，如果使用私有镜像进行创建，需要在制作私有镜像时安装特殊驱动。

## GPU驱动<a name="section1416112291151"></a>

如果这个私有镜像用于创建GPU加速型云服务器，需要在镜像中安装合适的GPU驱动来获得相应的GPU加速能力。GPU加速型实例中配备的NVIDIA Tesla GPU支持两种类型的驱动：Tesla驱动和GRID/vGPU驱动。

-   如果需要使用OpenGL/DirectX/Vulcan等图形加速能力，则需要安装GRID/vGPU驱动并自行配置使用GRID License。此外，GRID/vGPU驱动配合vDWS类型License，也支持CUDA，用来满足既需要计算加速也需要图形加速的场景。
-   如果需要使用NVIDIA CUDA计算加速能力，则需要安装Tesla驱动。

**表 1**  GRID驱动安装方法

<a name="table18701447205920"></a>
<table><thead align="left"><tr id="row10870124755917"><th class="cellrowborder" valign="top" width="29.959999999999997%" id="mcps1.2.3.1.1"><p id="p1845729208"><a name="p1845729208"></a><a name="p1845729208"></a>实例类型</p>
</th>
<th class="cellrowborder" valign="top" width="70.04%" id="mcps1.2.3.1.2"><p id="p1787010471594"><a name="p1787010471594"></a><a name="p1787010471594"></a>安装方法</p>
</th>
</tr>
</thead>
<tbody><tr id="row13870154714590"><td class="cellrowborder" valign="top" width="29.959999999999997%" headers="mcps1.2.3.1.1 "><p id="p98709475592"><a name="p98709475592"></a><a name="p98709475592"></a>G1型</p>
</td>
<td class="cellrowborder" valign="top" width="70.04%" headers="mcps1.2.3.1.2 "><p id="p9546243239"><a name="p9546243239"></a><a name="p9546243239"></a>请参见“<a href="https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0149610914.html#section2" target="_blank" rel="noopener noreferrer">下载GRID驱动及License软件包</a>”。</p>
</td>
</tr>
<tr id="row0870194735920"><td class="cellrowborder" valign="top" width="29.959999999999997%" headers="mcps1.2.3.1.1 "><p id="p08701147175915"><a name="p08701147175915"></a><a name="p08701147175915"></a>G3型</p>
</td>
<td class="cellrowborder" valign="top" width="70.04%" headers="mcps1.2.3.1.2 "><p id="p1777573951416"><a name="p1777573951416"></a><a name="p1777573951416"></a>请参见“<a href="https://support.huaweicloud.com/usermanual-ecs/zh-cn_topic_0149610914.html#section2" target="_blank" rel="noopener noreferrer">下载GRID驱动及License软件包</a>”。</p>
</td>
</tr>
</tbody>
</table>

