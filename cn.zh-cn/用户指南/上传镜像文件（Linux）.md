# 上传镜像文件（Linux）<a name="ims_01_0210"></a>

推荐您使用OBS Browser+工具将外部镜像文件上传至OBS个人桶，详细操作请参见“[OBS Browser+最佳实践](https://support.huaweicloud.com/browsertg-obs/obs_03_1006.html)”。

OBS Browser+工具下载方式：[https://support.huaweicloud.com/browsertg-obs/obs\_03\_1003.html](https://support.huaweicloud.com/browsertg-obs/obs_03_1003.html)

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   桶文件要和待注册的镜像属于同一区域。
>-   上传到OBS桶的外部镜像文件必须是非加密状态的或者采用SSE-KMS加密方式加密的文件。
>-   OBS桶和镜像文件的存储类别必须是标准存储。
>-   如果您希望在创建系统盘镜像时携带数据盘一起创建，还需要准备数据盘所在的镜像文件，并将该文件上传至OBS桶。最终将生成一个系统盘镜像、一个或多个（1\~3个）数据盘镜像。

