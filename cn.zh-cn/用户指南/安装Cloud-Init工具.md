# 安装Cloud-Init工具<a name="zh-cn_topic_0030730603"></a>

## 操作场景<a name="zh-cn_topic_0029124518_section2104193419393"></a>

为了保证使用私有镜像创建的新云服务器可以通过“用户数据注入”功能注入初始化自定义信息（例如为云服务器设置登录密码），请在创建私有镜像前安装Cloud-Init工具。

-   安装Cloud-Init工具时需要从官网下载并安装，因此，需要提前为云服务器绑定弹性公网IP。
-   不安装Cloud-Init工具，将无法对云服务器进行自定义配置，只能使用镜像原有密码登录云服务器。
-   使用公共镜像创建的云服务器，默认已经安装Cloud-Init，不需要执行安装及配置操作。
-   用户导入镜像创建的云服务器，请按照指导安装及配置Cloud-Init。配置Cloud-Init操作请参考[配置Cloud-Init工具](配置Cloud-Init工具.md)章节。

## 前提条件<a name="zh-cn_topic_0029124518_section49653222162416"></a>

-   已为云服务器绑定弹性公网IP。
-   已登录云服务器。
-   云服务器的网卡属性为DHCP方式。

## 安装步骤说明<a name="section62254326101255"></a>

1.  请先检查是否已安装Cloud-Init工具。

    具体操作请参考[检查是否已经安装Cloud-Init工具](#section57525650153449)。

2.  安装Cloud-Init工具。

    Cloud-Init安装方式分为：[采用官方提供的包源安装Cloud-Init工具（优先推荐）](#section9013470154018)、[采用官方提供的Cloud-Init源码包通过pip方式安装Cloud-Init工具](#section124220553610)和[采用官方源码编译安装方法](#section14939636151511)**。**


## 检查是否已经安装Cloud-Init工具<a name="section57525650153449"></a>

请先执行如下步骤检查是否已安装Cloud-Init工具。

在不同的操作系统下，查看是否已经安装Cloud-Init工具的方法不同。以CentOS 6系列为例，执行以下命令查看是否安装Cloud-Init工具。

**which cloud-init**

-   回显类似如下，表示已经安装Cloud-Init工具，无需重复安装。

    ```
    cloud-init-0.7.5-10.el6.centos.2.x86_64
    ```

-   无回显信息表示未安装Cloud-Init工具。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >由于Cloud-Init工具存在多种安装方法，如果无回显信息，请再次使用**rpm -qa |grep cloud-init**命令进行检查。**which cloud-init**和**rpm -qa |grep cloud-init**任何一个命令显示已安装，表示操作系统已安装Cloud-Init工具。


如果已安装Cloud-Init工具，还需要执行以下操作：

-   请确认当前云服务器操作系统中的证书是否继续使用。如果不再使用该证书，请删除证书。
    -   root用户对应目录下的文件（如“**_/$path/$to/$root_/**.ssh/authorized\_keys”），执行以下命令：

        **cd /root/.ssh**

        **rm authorized\_keys**

    -   非root用户对应目录下的证书文件（如“**_/$path/$to/$none-root_/**.ssh/authorized\_keys”），执行以下命令：

        **cd /home/centos/.ssh**

        **rm authorized\_keys**


-   执行以下命令，清除Cloud-Init工具产生的缓存，确保使用该私有镜像创建的云服务器可以使用证书方式登录。

    **sudo rm -rf /var/lib/cloud/\***


>![](public_sys-resources/icon-note.gif) **说明：** 
>设置完成后请勿重启云服务器，否则，需重新设置。

## 采用官方提供的包源安装Cloud-Init工具（优先推荐）<a name="section9013470154018"></a>

在不同操作系统的云服务器上安装Cloud-Init工具的方法不同，请在root用户下执行相关安装操作。

以下将介绍SUSE、CentOS、Fedora、Debian和Ubuntu操作系统安装Cloud-Init工具的具体方法。其他操作系统类型，请安装并配置对应类型的Cloud-Init工具，例如，使用CoreOS操作系统时需安装并配置coreos-cloudinit。

-   **SUSE操作系统**

    SUSE操作系统的Cloud-Init网络安装地址：

    [https://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools/](https://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools)

    [http://download.opensuse.org/repositories/Cloud:/Tools/](http://download.opensuse.org/repositories/Cloud:/Tools/)

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >在上述提供的网络安装地址下选择相应操作系统版本的repo安装包进行安装。

    以SUSE Enterprise Linux Server 12为例，Cloud-Init工具的安装步骤如下。

    1.  登录到创建Linux私有镜像所使用的云服务器。
    2.  执行以下命令，安装SUSE 12的网络安装源。

        **zypper ar https://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools/SLE\_12\_SP3/Cloud:Tools.repo**

    3.  执行以下命令，更新网络安装源。

        **zypper refresh**

    4.  执行以下命令，安装Cloud-Init。

        **zypper install cloud-init**

    5.  执行以下命令，设置Cloud-Init为开机自启动服务。

        -   SUSE 11：

            **chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

            **service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

        -   SUSE 12以及openSUSE 12/13/42：

            **systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

            **systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        >![](public_sys-resources/icon-caution.gif) **注意：** 
        >对于SUSE和openSUSE操作系统，请执行以下步骤禁止动态修改云服务器名称。
        >1.  执行以下命令，使用vi编辑器打开“dhcp”文件。
        >    **vi** **etc/sysconfig/network/dhcp**
        >2.  将“dhcp”文件中的“DHCLIENT\_SET\_HOSTNAME”的值修改为“no”。


-   **CentOS操作系统**

    CentOS操作系统的Cloud-Init网络安装地址如[表1](#table859383892814)所示。请在提供的网络安装地址下选择相应的epel-release安装包进行安装。

    **表 1**  Cloud-Init网络安装地址

|操作系统类型|版本|网络安装地址|
|--|--|--|
|CentOS|6系列32位|https://archives.fedoraproject.org/pub/archive/epel/6/i386/|
|6系列64位|https://archives.fedoraproject.org/pub/archive/epel/6/x86_64/|
|7系列64位|https://archives.fedoraproject.org/pub/epel/7/x86_64/Packages/e/|


    执行以下命令安装Cloud-Init：

    **yum install  _网络安装地址/_epel-release-**_**x-y**_**.noarch.rpm**

    **yum install cloud-init**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“网络安装地址”表示Cloud-Init对应的epel-release安装包的地址，_“__x-y”_表示当前操作系统对应的Cloud-Init epel-release版本号，执行命令时需参考[表1](#table859383892814)以及实际使用的安装包版本进行替换。
    >-   以CentOS 6系列64位为例，当前版本号为6.8，则命令修改为：
    >    **yum install https://archives.fedoraproject.org/pub/archive/epel/6/x86\_64/epel-release-6-8.noarch.rpm**
    >-   以CentOS 7系列64位为例，当前版本号为7.14。则命令修改为：
    >    **yum install https://archives.fedoraproject.org/pub/epel/7/x86\_64/Packages/e/epel-release-7-14.noarch.rpm**

-   **Fedora操作系统**

    安装Cloud-Init前，请确认操作系统已经配置好对应的网络安装源地址，请查看“/etc/yum.repo.d/fedora.repo”文件中是否已配置相关软件包安装源地址，如果没有配置相关地址源，请参考相关Fedora官网信息配置软件包安装源。

    执行以下命令，安装Cloud-Init。

    **yum install cloud-init**

-   **Debian和Ubuntu操作系统**

    安装Cloud-Init前，请确认操作系统已经配置好对应的网络安装源地址，请查看“/etc/apt/sources.list”文件中是否已配置相关软件包安装源地址，如果没有配置相关地址源，请参考Debian或者Ubuntu官网信息配置软件包安装源。

    执行以下命令，安装Cloud-Init。

    **apt-get update**

    **apt-get install** **cloud-init**


## 采用官方提供的Cloud-Init源码包通过pip方式安装Cloud-Init工具<a name="section124220553610"></a>

以cloud-init-0.7.9版本为例，Cloud-Init工具的安装步骤如下。

1.  下载cloud-init-0.7.9.tar.gz源码包（推荐优先选用0.7.9版本），上传到云服务器指定目录“/home/”下。

    cloud-init-0.7.9.tar.gz源码包下载地址：

    [https://launchpad.net/cloud-init/trunk/0.7.9/+download/cloud-init-0.7.9.tar.gz](https://launchpad.net/cloud-init/trunk/0.7.9/+download/cloud-init-0.7.9.tar.gz)

2.  在“\~/.pip/”目录下新建pip.conf文件，编辑内容如下。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >“\~/.pip/”若不存在，可使用命令**mkdir \~/.pip**命令新建。

    ```
    [global]
    index-url  = https://<$mirror>/simple/
    trusted-host = <$mirror>
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >编辑内容中**<$mirror\>**部分可以选择公网PyPI源或教育网PyPI源进行替换。
    >-   公网PyPI源：[https://pypi.python.org/](https://pypi.python.org/)
    >-   教育网PyPI源：[https://pypi.tuna.tsinghua.edu.cn/](https://pypi.tuna.tsinghua.edu.cn/)
    >    [https://pypi.mirrors.ustc.edu.cn/](https://pypi.mirrors.ustc.edu.cn/)

3.  执行以下命令，安装本地下载的Cloud-Init源码包，安装过程中根据需要选择**--upgrade**参数。

    **pip install \[--upgrade\] /home/cloud-init-0.7.9.tar.gz**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >安装Cloud-Init源码包的更多信息，请参见[cloud-init官方文档](http://cloudinit.readthedocs.io/?spm=a2c4g.11186623.0.0.c8bb67b7NIX4Oa)。

4.  执行命令**cloud-init -v**，如回显如下类似信息表示安装Cloud-Init成功。

    ```
    cloud-init 0.7.9
    ```

5.  设置Cloud-Init相关服务为开机自启动。
    -   若操作系统是sysvinit自启动管理服务，则执行以下命令进行设置。

        **chkconfig --add cloud-init-local; chkconfig --add cloud-init; chkconfig --add cloud-config; chkconfig --add cloud-final**

        **chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

        **service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

    -   若操作系统是systemd自启动管理服务，则执行以下命令进行设置。

        **systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        **systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**



>![](public_sys-resources/icon-caution.gif) **注意：** 
>采用官方提供的Cloud-Init源码包通过pip方式进行安装时要注意以下两点。
>1.  Cloud-Init安装时需要添加syslog用户到adm组。存在syslog用户时直接添加syslog用户到adm组。不存在syslog用户时（如CentOS和SUSE），执行下列命令创建syslog用户，添加到adm组：
>    **useradd syslog**
>    **groupadd adm**
>    **usermod -g adm syslog**
>2.  在“/etc/cloud/cloud.cfg”中system\_info部分的distro要根据具体操作系统发行版本做相应修改（如根据具体操作系统发行版相应修改为：**distro: ubuntu**，**distro: sles**，**distro: debian**，**distro: fedora**）。

## 采用官方源码编译安装方法****<a name="section14939636151511"></a>

官方源码编译安装方法****的Cloud-Init工具Github开源地址：[https://github.com/canonical/cloud-init/](https://github.com/canonical/cloud-init/)

1.  执行以下命令，下载Cloud-Init压缩包，并将其复制至新建的“/tmp/CLOUD-INIT”文件夹。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >0.7.6版本安装包下载地址：[https://github.com/canonical/cloud-init/archive/refs/tags/0.7.6.zip](https://github.com/canonical/cloud-init/archive/refs/tags/0.7.6.zip)
    >0.7.9版本安装包下载地址：[https://github.com/canonical/cloud-init/archive/refs/tags/0.7.9.zip](https://github.com/canonical/cloud-init/archive/refs/tags/0.7.9.zip)
    >Cloud-Init所有版本安装包下载地址：[https://github.com/canonical/cloud-init/releases](https://github.com/canonical/cloud-init/releases)

    **wget** **https://github.com/canonical/cloud-init/archive/refs/tags/0.7.6.zip**

    **mkdir /tmp/CLOUD-INIT**

    **cp  **cloud-init-0.7.6.zip**  /tmp/CLOUD-INIT**

    **cd /tmp/CLOUD-INIT**

2.  执行如下命令，解压Cloud-Init压缩包。

    **unzip  **cloud-init-0.7.6.zip****

3.  执行如下命令进入cloud-init-0.7.6文件夹。

    **cd  **cloud-init**-0.7.6**

4.  若cloud-init为18.3\~22.3版本，则需要进行如下适配。否则跳过本步骤，继续执行下一步。

    **sed -i '/VALID\_DMI\_ASSET\_TAGS =/a\\VALID\_DMI\_ASSET\_TAGS += \["HUAWEICLOUD"\]' cloudinit/sources/DataSourceOpenStack.py**

    **cat cloudinit/sources/DataSourceOpenStack.py | grep VALID\_DMI\_ASSET\_TAGS**

    确认执行结果如下图，表示语句添加成功。

    ![](figures/zh-cn_image_0000001390619817.png)

5.  按照操作系统类型，执行相应的命令安装Cloud-Init安装包。

    -   CentOS6.x/SUSE11.x：

        **python setup.py build**

        **python setup.py install --init-system sysvinit**

    -   CentOS7.x/SUSE12.x：

        **python setup.py build**

        **python setup.py install --init-system systemd**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >Cloud-Init安装时需要添加syslog用户到adm组。存在syslog用户时直接添加syslog用户到adm组。不存在syslog用户时（如CentOS和SUSE），执行下列命令创建syslog用户，添加到adm组：
    >**useradd syslog**
    >**groupadd adm**
    >**usermod -g adm syslog**

6.  设置Cloud-Init相关服务为开机自启动。
    -   若操作系统是sysvinit自启动管理服务，则执行以下命令进行设置。

        **chkconfig --add cloud-init-local; chkconfig --add cloud-init; chkconfig --add cloud-config; chkconfig --add cloud-final**

        **chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

        **service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

    -   若操作系统是systemd自启动管理服务，则执行以下命令进行设置。

        **systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        **systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

7.  执行如下命令检查Cloud-Init是否安装成功。

    **cloud-init -v**

    **cloud-init init --local**

    回显如下类似信息所示表示安装Cloud-Init成功。

    ```
    cloud-init 0.7.6
    ```


