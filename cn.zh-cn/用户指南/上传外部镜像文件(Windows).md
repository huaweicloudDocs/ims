# 上传外部镜像文件\(Windows\)<a name="ZH-CN_TOPIC_0030713183"></a>

注册镜像前，请上传外部镜像文件到OBS桶。

当前云平台支持导入vhd、vmdk、qcow2、raw、vhdx、qcow、vdi、qed、zvhd或zvhd2等格式镜像文件创建私有镜像。推荐使用qcow2格式的镜像文件。如果您需要导入其他格式的镜像，请先使用qemu-img工具转换镜像的格式后再导入。导入的镜像文件必须为单一的镜像文件，例如pre-allocated格式镜像依赖2个文件："xxxx.vmdk" 和"xxxx-flat.vmdk"，这两种格式的镜像文件不能直接导入到云平台，需提前转换成通用的vmdk或qcow2格式才能导入。

镜像格式转换请参考《镜像服务最佳实践》中“镜像格式转换”章节。

请使用OBS Browser工具上传外部镜像文件，具体操作请参见《对象存储服务客户端指南（OBS Browser）》。

上传到OBS桶的外部镜像文件必须是非加密状态的或者采用SSE-KMS加密方式加密的文件。

上传外部镜像文件到OBS桶时，OBS桶和镜像文件的存储类别必须是OBS标准存储。

请点击如下链接下载OBS Browser工具：

[http://static.huaweicloud.com/upload/files/tools/OBSBrowser.zip](http://static.huaweicloud.com/upload/files/tools/OBSBrowser.zip)

