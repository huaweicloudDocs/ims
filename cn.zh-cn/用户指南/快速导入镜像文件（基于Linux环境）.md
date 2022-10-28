# 快速导入镜像文件（基于Linux环境）<a name="ims_01_0340"></a>

## 操作场景<a name="section12126161523313"></a>

本节指导您基于Linux操作系统环境完成镜像文件快速导入，推荐使用云平台的EulerOS云服务器作为转换镜像格式和生成位表文件的环境。

Linux操作系统环境下，建议使用qemu-img-hw工具进行镜像格式转换。

## 前提条件<a name="section1892165619595"></a>

-   已完成镜像文件优化，详细操作请参考[优化过程（Windows）](优化过程（Windows）.md)或[优化过程（Linux）](优化过程（Linux）.md)；同时需要确保镜像文件符合[表1](准备镜像文件（Windows）.md#table85212269215)或[表1](准备镜像文件（Linux）.md#table85212269215)中的限制条件。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >根据镜像文件的操作系统类型来选择所参考内容。

-   已在管理控制台创建EulerOS操作系统的弹性云服务器，并确保云服务器已绑定弹性公网IP。
-   已在管理控制台创建OBS桶。

## 操作步骤<a name="section745217198110"></a>

1.  上传镜像文件至云服务器。
    -   本地主机为Linux系统：

        通过scp命令将镜像文件上传至云服务器。以将“image01.qcow2”文件上传至云服务器的“/usr/”目录下为例。

        **scp** **/var/image01.qcow2** **root@**_xxx.xxx.xx.xxx_**:/usr/**

        其中，_xxx.xxx.xx.xxx_为云服务器的弹性公网IP。

    -   本地主机为Windows系统：

        使用文件传输工具（例如WinSCP）将镜像文件上传至云服务器。

2.  获取镜像转换工具（qemu-img-hw.zip）和位表文件生成工具（createMF.zip），并上传至云服务器，然后解压工具包。

    **表 1**  工具获取方式

|工具包|下载地址|
|--|--|
|qemu-img-hw.zip|https://cn-south-1-cloud-reset-pwd.obs.cn-south-1.myhuaweicloud.com/imageImportTools/qemu-img-hw.zip|
|createMF.zip|https://cn-south-1-cloud-reset-pwd.obs.cn-south-1.myhuaweicloud.com/imageImportTools/createMF.zip|


3.  使用qemu-img-hw工具转换镜像格式。
    1.  进入qemu-img-hw存放目录，以存放在“/usr/qemu-img-hw”为例：

        **cd** **/usr/qemu-img-hw**

    2.  执行以下命令修改权限：

        **chmod** **+x** **qemu-img-hw**

    3.  执行qemu-img-hw命令将镜像文件转为zvhd2或raw格式（推荐转为zvhd2格式）。

        qemu-img-hw命令格式：

        **./qemu-img-hw** **convert** **-p** **-O** _\{目标镜像格式\}_ _\{待转换镜像文件\}_ _\{目标镜像文件\}_

        以将“image01.qcow2”格式文件转换成“image01.zvhd2”格式为例：

        **./qemu-img-hw** **convert** **-p** **-O** **zvhd2** **image01.qcow2** **image01.zvhd2**

        -   若转换后为zvhd2格式文件，请执行[5](#li12136151722)。
        -   若转换后为raw格式文件，请使用CreateMF.jar工具，生成raw格式镜像文件的位表文件。请执行[4](#li1683153619217)。

4.  <a name="li1683153619217"></a>使用CreateMF.jar工具生成位表文件。
    1.  请确保当前云服务器已安装jdk。

        执行以下命令查看是否已安装jdk：

        **source** **/etc/profile**

        **java** **-version**

        如果回显信息中显示java版本信息，证明当前云服务器已安装jdk。

    2.  执行以下命令进入CreateMF.jar程序所在的目录。

        **cd** **/usr/createMF**

    3.  执行以下命令生成位表文件。

        **java** **-jar** **CreateMF.jar** _/__原raw文件路径_ _/__生成的mf文件路径_

        例如：

        **java** **-jar** **CreateMF.jar** **image01.raw** **image01.mf**

        >![](public_sys-resources/icon-caution.gif) **注意：** 
        >生成的.mf位表文件和raw格式镜像文件必须是相同名称。例如镜像文件名称为：image01.raw，那么生成的位表文件名称为：image01.mf。


5.  <a name="li12136151722"></a>使用s3cmd工具上传文件至OBS桶。
    1.  安装s3cmd工具。

        若云服务器已安装该工具可跳过此步骤，直接进行第二步配置s3cmd：

        1.  执行以下命令，安装setuptools。

            **yum** **install** **python-setuptools**

        2.  执行以下命令，安装wget。

            **yum** **install** **wget**

        3.  执行以下命令，获取s75pxd软件包：

            **wget** **https://github.com/s3tools/s3cmd/archive/master.zip**

            **mv** **master.zip** **s3cmd-master.zip**

        4.  执行以下命令，安装s3cmd：

            **unzip** **s3cmd-master.zip**

            **cd** **s3cmd-master**

            **python** **setup.py** **install**

    2.  配置s3cmd工具。

        执行以下命令配置s3cmd工具。

        ```
        s3cmd --configure
        Access Key: 输入AK
        Secret Key: 输入SK
        Default Region: 输入所在Region
        S3 Endpoint: 可参考OBS的Endpoint
        DNS-style bucket+hostname:port template for accessing a bucket: 输入带桶名的Server地址，例如mybucket.obs.myclouds.com
        Encryption password: 不填，直接按回车
        Path to GPG program: 不填，直接按回车
        Use HTTPS protocol: 是否使用HTTPS，Yes/No
        HTTP Proxy server name: 代理地址，连接云平台需要连外网（如不需要直接回车）
        HTTP Proxy server port: 代理端口，连接云平台需要连外网（如不需要直接回车）
        Test access with supplied credentials? y
        （如果显示：Success. Your access key and secret key worked fine :-) 则表示连接成功）
        Save settings? y（是否保存配置）
        ```

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >配置完成后，信息会保存在用户目录下“/root/.s3cfg”，如果还想修改，可以重新执行**s3cmd** **--configure**命令，或者直接编辑.s3cfg文件（执行**vi** **.s3cfg**命令进行编辑）。

    3.  使用s3cmd命令上传zvhd2格式镜像文件到OBS桶，或者上传raw格式镜像文件及其位表文件到OBS桶。

        **s3cmd** **put** _image01.zvhd2_ **s3://**_mybucket_**/**

        >![](public_sys-resources/icon-caution.gif) **注意：** 
        >.mf位表文件必须和其对应的raw格式镜像文件在同一个OBS桶中。


6.  注册私有镜像。

    您可以通过控制台方式、API接口方式，将转换后的zvhd2或raw文件注册为私有镜像。

    **方法一：通过控制台创建私有镜像**

    1.  登录IMS控制台。
        1.  登录管理控制台。
        2.  选择“计算 \> 镜像服务”。

            进入镜像服务页面。

    2.  单击右上角的“创建私有镜像”。
    3.  在“镜像类型和来源”页面，选择镜像的创建方式为“系统盘镜像”或“数据盘镜像”。
    4.  镜像的源选择为“镜像文件”，从列表中选择转换为zvhd2或raw文件的桶，再选择转换后的镜像文件。如果是raw格式镜像文件，还需要选择位表文件。
    5.  勾选快速通道栏的“开启快速通道”，并确认已优化镜像文件，然后勾选“镜像文件准备”栏的内容。

        **图 1**  快速导入镜像文件<a name="fig277285611573"></a>  
        ![](figures/快速导入镜像文件.png "快速导入镜像文件")

    6.  根据界面提示填写配置信息。

        具体的配置参数说明，请参见[注册镜像（Linux）](注册镜像（Linux）.md)。

        >![](public_sys-resources/icon-caution.gif) **注意：** 
        >-   操作系统必须要和镜像文件所含的操作系统一致。
        >-   系统盘大小必须大于镜像文件的大小。
        >    通过qemu-img-hw工具可查询镜像文件大小：
        >    **qemu-img-hw** **info** _test.zvhd2_


    **方法二：通过API方式创建私有镜像**

    您可以通过接口POST /v2/cloudimages/quickimport/action，实现镜像文件快速导入功能。

    该接口的具体调用方法，请参见“[镜像文件快速导入](https://support.huaweicloud.com/api-ims/ims_03_0605.html)”。


## 附1：qemu-img-hw常用命令<a name="section962713814611"></a>

-   镜像文件格式转换：**qemu-img-hw** **convert** **-p** **-O** _\{目标镜像格式\}_ _\{待转换镜像文件\}_ _\{目标镜像文件\}_

    上述命令中各参数对应的说明如下：

    -p：标识转换的进度条

    -O：（必须是大写）后面的参数为转换出来的镜像格式 + 源镜像文件名称 + 目标镜像文件名称

    示例：将qcow2格式转为zvhd2格式

    **qemu-img-hw** **convert** **-p** **-O** **zvhd2** **test.qcow2** **test.zvhd2**

-   查询镜像文件信息：**qemu-img-hw** **info** _\{镜像文件\}_

    示例：**qemu-img-hw** **info** **test.zvhd2**

-   查看帮助：**qemu-img-hw** **-help**

## 附2：执行qemu-img-hw常见报错<a name="section168872043899"></a>

-   问题描述：

    执行qemu-img-hw命令时回显信息如下：

    ```
    ./qemu-img-hw: /lib64/libc.so.6: version `GLIBC_2.14' not found (required by ./qemu-img-hw)
    ```

    解决方法：

    执行**strings** **/lib64/libc.so.6** **|** **grep** **GLIBC**查看GLIBC版本，若由于版本过低造成，可安装高版本即可。依次执行下述命令：

    **wget** **http://ftp.gnu.org/gnu/glibc/glibc-2.15.tar.gz**

    **wget** **http://ftp.gnu.org/gnu/glibc/glibc-ports-2.15.tar.gz**

    **tar** **-xvf** **glibc-2.15.tar.gz**

    **tar** **-xvf** **glibc-ports-2.15.tar.gz**

    **mv** **glibc-ports-2.15** **glibc-2.15/ports**

    **mkdir** **glibc-build-2.15**

    **cd** **glibc-build-2.15**

    **../glibc-2.15/configure** **--prefix=/usr** **--disable-profile** **--enable-add-ons** **--with-headers=/usr/include** **--with-binutils=/usr/bin**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >此命令若报错“configure: error: no acceptable C compiler found in $PATH”，请先执行：**yum** **-y** **install** **gcc**

    **make**

    **make** **install**

-   问题描述：

    执行qemu-img-hw命令时回显信息如下：

    ```
    ./qemu-img-hw: error while loading shared libraries: libaio.so.1: cannot open shared object file: No such file or directory
    ```

    解决方法：请先执行命令**yum** **install** **libaio**


