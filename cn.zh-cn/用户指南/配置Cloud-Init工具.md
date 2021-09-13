# 配置Cloud-Init工具<a name="ims_01_0407"></a>

## 操作场景<a name="section3973140152118"></a>

Cloud-Init工具安装完成后，请参考本节操作配置Cloud-Init工具。

## 前提条件<a name="zh-cn_topic_0029124518_section49653222162416"></a>

-   已安装Cloud-Init工具。
-   已为云服务器绑定弹性公网IP。
-   已登录云服务器。
-   云服务器的网卡属性为DHCP方式。

## 配置步骤说明<a name="section62254326101255"></a>

包含如下两步操作：

1.  配置Cloud-Init工具。

    具体操作请参考[配置Cloud-Init工具](#section167211112174518)。

2.  检查Cloud-Init工具相关配置是否成功。

    具体操作请参考[检查Cloud-Init工具相关配置是否成功](#section56956574101031)。


## 配置Cloud-Init工具<a name="section167211112174518"></a>

1.  用户可以根据需要根据用户类型配置登录云服务器的用户权限。使用root帐户登录，需要开启root用户的ssh权限，并开启密码远程登录。

    -   若用户选择注入密码，则通过自己注入的密码进行远程SSH或noVNC登录。
    -   若用户选择注入密钥，则通过自己注入的密钥进行远程SSH登录。

    执行以下命令，在vi编辑器中打开“/etc/cloud/cloud.cfg”。

    **vi /etc/cloud/cloud.cfg**

2.  （可选）在“/etc/cloud/cloud.cfg”中配置“apply\_network\_config”为“false”。

    对于使用Cloud-Init 18.3及以上版本的用户，需执行本操作。

    **图 1**  配置示例<a name="ims_01_0407_fig1561411173116"></a>  
    ![](figures/配置示例.png "配置示例")

3.  设置开放root密码远程登录并开启root用户的ssh权限。以CentOS 6.7系列操作系统为例，配置文件中的“disable\_root“字段为“1“表示为禁用，为“0“表示不禁用（部分OS的Cloud-Init配置使用“true“表示禁用，“false“表示不禁用）。设置“disable\_root“值为“0“，“ssh\_pwauth“为“1“，“lock\_passwd“设置为“false“，“false“表示不锁住用户密码。

    ```
    users:
     - name: root
       lock_passwd: False
    
    disable_root: 0
    ssh_pwauth: 1
    ```


1.  开启机器名更新机制，请勿注释或删除“ - update\_hostname”语句。

    ```
    cloud_init_modules:
     - migrator
     - bootcmd
     - write-files
     - growpart
     - resizefs
     - set_hostname
     - update_hostname
     - update_etc_hosts
     - rsyslog
     - users-groups
     - ssh
    ```

2.  执行以下命令，在vi编辑器中打开“/etc/ssh/sshd\_config”。

    **vi /etc/ssh/sshd\_config**

3.  将“sshd\_config”中的“PasswordAuthentication”的值修改为“yes”。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如果是SUSE和openSUSE操作系统，需要同时配置“sshd\_config”文件中的以下两个参数为“yes”。
    >-   PasswordAuthentication
    >-   ChallengeResponseAuthentication

4.  确保删除镜像模板中已经存在的linux帐户和“/home/linux”目录。

    **userdel linux**

    **rm -fr /home/linux**


1.  配置agent访问OpenStack数据源。

    在“/etc/cloud/cloud.cfg”最后一行添加如下内容，配置agent访问OpenStack数据源。

    ```
    datasource_list: [ OpenStack ]
    datasource:
      OpenStack:
        metadata_urls: ['http://169.254.169.254']
        max_wait: 120
        timeout: 5
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   max\_wait和timeout可由用户自定义是否需要配置，上述回显信息中max\_wait和timeout的取值仅供参考。
    >-   当操作系统版本低于Debian8、CentOS 5时，不支持配置agent访问OpenStack数据源。
    >-   CentOS、EulerOS操作系统云服务器必须要禁用默认的zeroconf路由，以便精确访问OpenStack数据源。
    >    **echo "NOZEROCONF=yes" \>\> /etc/sysconfig/network**

2.  在配置文件“/etc/cloud/cloud.cfg”中禁用Cloud-Init接管网络。

    当Cloud-Init版本等于或高于0.7.9版本时，在配置文件“/etc/cloud/cloud.cfg”中增加如下内容，禁用Cloud-Init接管网络。

    ```
    network:
      config: disabled
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >增加的内容需严格按照yaml格式进行配置。

    **图 2**  禁用Cloud-Init接管网络<a name="fig6457310396"></a>  
    ![](figures/禁用Cloud-Init接管网络.png "禁用Cloud-Init接管网络")

3.  在配置文件“/etc/cloud/cloud.cfg”中补充如下内容。

    **manage\_etc\_hosts: localhost**

    防止启动云服务器时，系统长时间卡在“Waiting for cloudResetPwdAgent”状态。

    **图 3**  新增manage\_etc\_hosts: localhost<a name="fig12642166911"></a>  
    ![](figures/新增manage_etc_hosts-localhost.png "新增manage_etc_hosts-localhost")

4.  修改配置文件“cloud\_init\_modules”。

    在“cloud\_init\_modules”中将ssh从最后提前到第一位处理，提高云服务器ssh登录速度。

    **图 4**  提高云服务器ssh登录速度<a name="fig1790810621020"></a>  
    ![](figures/提高云服务器ssh登录速度.png "提高云服务器ssh登录速度")

5.  修改以下配置使得镜像创建的云服务器主机名不带“.novalocal”后缀且主机名称中可以带点号。
    1.  执行如下命令，修改“\_\_init\_\_.py”文件。

        **vi /usr/lib/python2.7/site-packages/cloudinit/sources/\_\_init\_\_.py**

        按“i”进入编辑模式，根据关键字toks查询，修改内容如下回显信息所示。

        ```
        if toks:
            toks = str(toks).split('.')
        else:
            toks = ["ip-%s" % lhost.replace(".", "-")]
        else:
            toks = lhost.split(".novalocal")
        
        if len(toks) > 1:
            hostname = toks[0]
            #domain = '.'.join(toks[1:])
        else:
            hostname = toks[0]
        
        if fqdn and domain != defdomain:
            return "%s.%s" % (hostname, domain)
        else:
            return hostname
        ```

        修改完成后按“ESC”退出编辑模式，输入**:wq!**保存并退出。

        **图 5**  修改\_\_init\_\_.py文件<a name="fig16394117429"></a>  
        ![](figures/修改__init__-py文件.png "修改__init__-py文件")

    2.  执行如下命令进入“cloudinit/sources”文件夹。

        **cd /usr/lib/python2.7/site-packages/cloudinit/sources/**

    3.  执行如下命令，删除“\_\_init\_\_.pyc”文件和优化编译后的“\_\_init\_\_.pyo”文件。

        **rm -rf \_\_init\_\_.pyc**

        **rm -rf \_\_init\_\_.pyo**

    4.  执行如下命令，清理日志信息。

        **rm -rf /var/lib/cloud/\***

        **rm -rf /var/log/cloud-init\***

6.  执行以下命令编辑Cloud-Init日志输出路径配置文件，设置日志处理方式handlers，建议配置为cloudLogHandler。

    **vim /etc/cloud/cloud.cfg.d/05\_logging.cfg**

    **图 6**  配置为cloudLogHandler<a name="fig7199201371212"></a>  
    ![](figures/配置为cloudLogHandler.png "配置为cloudLogHandler")


## 检查Cloud-Init工具相关配置是否成功<a name="section56956574101031"></a>

执行以下命令，无错误发生，说明Cloud-Init配置成功。

**cloud-init init --local**

正确安装的Cloud-Init会显示Cloud-Init的版本详细信息，并且无任何错误信息。例如，正确安装的情况下，不含有缺少文件的提示信息。

>![](public_sys-resources/icon-note.gif) **说明：** 
>执行如下命令，可将系统用户密码有效期设置为最大。此操作可选。
>**chage -M 99999 $user\_name**
>其中，user\_name为系统用户，例如root帐户。
>密码有效期建议设置为99999。

