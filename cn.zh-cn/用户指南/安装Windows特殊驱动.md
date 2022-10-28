# 安装Windows特殊驱动<a name="ims_01_0404"></a>

## 操作场景<a name="section273431714186"></a>

对于一些类型的弹性云服务器，如果使用私有镜像进行创建，需要在制作私有镜像时安装特殊驱动。

## GPU驱动<a name="section1416112291151"></a>

如果这个私有镜像用于创建GPU加速型云服务器，需要在镜像中安装合适的GPU驱动来获得相应的GPU加速能力。GPU加速型实例中配备的NVIDIA Tesla GPU支持两种类型的驱动：Tesla驱动和GRID/vGPU驱动。

-   如果需要使用OpenGL/DirectX/Vulcan等图形加速能力，则需要安装GRID/vGPU驱动并自行配置使用GRID License。此外，GRID/vGPU驱动配合vDWS类型License，也支持CUDA，用来满足既需要计算加速也需要图形加速的场景。
-   如果需要使用NVIDIA CUDA计算加速能力，则需要安装Tesla驱动。

**表 1**  GRID驱动安装方法

|实例类型|安装方法|
|--|--|
|G1型|请参见“下载GRID驱动及License软件包”。|
|G3型|请参见“下载GRID驱动及License软件包”。|


