# 使用s3cmd上传文件<a name="ZH-CN_TOPIC_0133773782"></a>

1.  安装s3cmd工具。

    若系统已安装该工具可跳过此步骤，直接进行第二步配置s3cmd：

    1.  执行以下命令，安装setuptools。

        **yum install python-setuptools**

    2.  执行以下命令，安装wget。

        **yum install wget**

    3.  执行以下命令，获取s75pxd软件包:

        **wget https://github.com/s3tools/s3cmd/archive/master.zip**

        **mv master.zip s3cmd-master.zip**

    4.  执行以下命令，安装s3cmd:

        **unzip s3cmd-master.zip**

        **cd s3cmd-master**

        **python setup.py install**


2.  配置s3cmd工具。

    执行以下命令配置s3cmd工具。

    ```
    s3cmd --configure
    Access Key: 输入AK
    Secret Key: 输入SK
    Default Region: 输入所在region
    S3 Endpoint: 可参考obs的endpoint
    DNS-style bucket+hostname:port template for accessing a bucket: 带桶名的server地址,例如%(bucket)s.obs.myclouds.com
    Encryption password: 不填，直接按回车
    Path to GPG program: 不填，直接按回车
    Use HTTPS protocol: 是否使用使用HTTPS，Yes/No
    HTTP Proxy server name: 代理地址，连接公有云/云道需要连外网（如不需要直接回车）。
    HTTP Proxy server port: 代理端口，连接公有云/云道需要连外网（如不需要直接回车）。
    Test access with supplied credentials? y
    （如果显示：Success. Your access key and secret key worked fine :-) 则表示连接成功）
    Save settings? y（是否保存配置）
    ```

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >配置完成后，会被保存在用户目录下/root/.s3cfg，如果还想修改可以重新执行**s3cmd --configure**命令，或者直接编辑.s3cfg文件（执行**vi .s3cfg**命令进行编辑）。  

3.  使用s3cmd命令上传**image.qcow2**格式镜像建到mybucket桶。

    **s3cmd put image.qcow2 s3://mybucket/**


