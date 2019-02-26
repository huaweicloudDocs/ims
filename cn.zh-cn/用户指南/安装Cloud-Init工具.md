# 安装Cloud-Init工具<a name="ZH-CN_TOPIC_0030730603"></a>

为了保证使用私有镜像创建的新云服务器可以自定义配置（例如修改云服务器密码），请在创建私有镜像前安装Cloud-Init工具。

## 操作场景<a name="zh-cn_topic_0029124518_section2104193419393"></a>

-   Linux操作系统安装Cloud-Init工具时需要从官网下载并安装，因此，需要提前给云服务器配置弹性IP。
-   不安装Cloud-Init工具，将无法对云服务器进行自定义配置，只能使用镜像原有密码登录云服务器。
-   使用公共镜像创建的云服务器，默认已经安装Cloud-Init，不需要执行安装及配置操作。
-   用户导入镜像创建的云服务器，请按照指导安装及配置Cloud-Init。配置Cloud-Init操作请参考[配置Cloud-Init工具](配置Cloud-Init工具.md)章节。

## 前提条件<a name="zh-cn_topic_0029124518_section49653222162416"></a>

-   已为Linux云服务器绑定弹性IP。
-   已登录Linux云服务器。
-   Linux云服务器的网卡属性为DHCP方式。

## 安装方式<a name="section62254326101255"></a>

1.  请先检查是否已安装Cloud-Init工具。

    具体操作请参考[检查是否已经安装Cloud-Init工具](#section57525650153449)。

2.  安装Cloud-Init工具。

    Cloud-Init安装方式分为：[采用官方提供的包源安装Cloud-Init工具（优先推荐）](#section9013470154018)、[采用官方提供的cloud-init源码包通过pip方式安装Cloud-Init工具](#section124220553610)和[采用源码编译安装方法](#section14939636151511)**。**


## 检查是否已经安装Cloud-Init工具<a name="section57525650153449"></a>

请先执行如下步骤检查是否已安装Cloud-Init工具。

在不同的操作系统下，查看是否已经安装Cloud-Init工具的方法不同，以CentOS 6 系列为例，执行以下命令查看是否安装Cloud-Init工具。

**rpm -qa |grep cloud-init**

-   回显类似如下，表示已经Cloud-Init工具，无需进行安装Cloud-Init工具的操作。

    ```
    cloud-init-0.7.5-10.el6.centos.2.x86_64
    ```

    -   请确认当前云服务器操作系统中的证书是否继续使用，如果不再使用该证书，请删除证书。
        -   root用户对应目录下的文件（如“**_/$path/$to/$root_/**.ssh/authorized\_keys”）执行以下命令。

            **cd /root/.ssh**

            **rm authorized\_keys**

        -   非root用户对应目录下的证书文件（如“**_/$path/$to/$none-root_/**.ssh/authorized\_keys”），执行以下命令。

            **cd /home/centos/.ssh**

            **rm authorized\_keys**


    -   执行以下命令，确保Linux镜像创建的云服务器可以使用创建云服务器证书方式登录。

        **sudo rm -rf /var/lib/cloud/\***


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >设置完成后请勿重启云服务器，否则，需重新设置。  


## 采用官方提供的包源安装Cloud-Init工具（优先推荐）<a name="section9013470154018"></a>

在不同操作系统的云服务器上安装Cloud-Init工具的方法不同，请在root用户下执行相关安装操作。

以下将介绍SUSE、CentOS、Red Hat、Fedora、Debian和Ubuntu操作系统安装Cloud-Init工具的具体方法。其他操作系统类型，请安装并配置对应的类型的Cloud-Init工具，例如，使用CoreOS操作系统时需安装并配置coreos-cloudinit。

-   **SUSE操作系统**

    SUSE操作系统的Cloud-Init网络安装地址：

    [http://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools/](http://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools)

    [http://download.opensuse.org/repositories/Cloud:/Tools/](http://download.opensuse.org/repositories/Cloud:/Tools/)

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >在上述提供的网络安装地址下选择相应的操作系统版本的repo安装包进行安装。  

    以SUSE Enterprise Linux Server 11 SP4为例，Cloud-Init工具的安装步骤如下。

    1.  登录到创建Linux私有镜像所使用的云服务器。
    2.  执行以下命令，安装SUSE 11 SP4的网络安装源。

        **zypper ar http://ftp5.gwdg.de/pub/opensuse/repositories/Cloud:/Tools/SLE\_11\_SP4/Cloud:Tools.repo**

    3.  执行以下命令，更新网络安装源。

        **zypper refresh**

    4.  执行以下命令，安装Cloud-Init。

        **zypper install cloud-init**

    5.  执行以下命令，设置Cloud-Init为开机自启动服务。

        -   SUSE 11 ：

        **chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

        **service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

        -   SUSE 12 以及OpenSUSE 12/13/42：

        **systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        **systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        >![](public_sys-resources/icon-notice.gif) **注意：**   
        >对于SUSE和OpenSUSE操作系统，请执行以下步骤禁止动态修改云服务器名称。  
        >1.  执行以下命令，使用vi编辑器打开“dhcp”文件。  
        >    **vi etc/sysconfig/network/dhcp**  
        >2.  将“dhcp”文件中的“DHCLIENT\_SET\_HOSTNAME”的值修改为“no”。  


-   **CentOS和Red Hat系列操作系统**

    CentOS和Red Hat系列操作系统的Cloud-Init网络安装地址如[表1](#table859383892814)所示。请在提供的网络安装地址下选择相应的epel-release安装包进行安装。

    **表 1**  Cloud-Init网络安装地址

    <a name="table859383892814"></a>
    <table><thead align="left"><tr id="row135773383280"><th class="cellrowborder" valign="top" width="18.86%" id="mcps1.2.4.1.1"><p id="p185771338112811"><a name="p185771338112811"></a><a name="p185771338112811"></a>操作系统类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="16.42%" id="mcps1.2.4.1.2"><p id="p3577938132810"><a name="p3577938132810"></a><a name="p3577938132810"></a>版本</p>
    </th>
    <th class="cellrowborder" valign="top" width="64.72%" id="mcps1.2.4.1.3"><p id="p18577113811282"><a name="p18577113811282"></a><a name="p18577113811282"></a>网络安装地址</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1759320380286"><td class="cellrowborder" rowspan="2" valign="top" width="18.86%" headers="mcps1.2.4.1.1 "><p id="p2593238202813"><a name="p2593238202813"></a><a name="p2593238202813"></a>CentOS、Red Hat或Oracle Linux</p>
    </td>
    <td class="cellrowborder" valign="top" width="16.42%" headers="mcps1.2.4.1.2 "><p id="p8593163882820"><a name="p8593163882820"></a><a name="p8593163882820"></a>6系列32位</p>
    </td>
    <td class="cellrowborder" valign="top" width="64.72%" headers="mcps1.2.4.1.3 "><p id="p2059312384284"><a name="p2059312384284"></a><a name="p2059312384284"></a><a href="https://dl.fedoraproject.org/pub/epel/6/i386/" target="_blank" rel="noopener noreferrer">https://dl.fedoraproject.org/pub/epel/6/i386/</a></p>
    </td>
    </tr>
    <tr id="row11593143822818"><td class="cellrowborder" valign="top" headers="mcps1.2.4.1.1 "><p id="p6593163810285"><a name="p6593163810285"></a><a name="p6593163810285"></a>6系列64位</p>
    </td>
    <td class="cellrowborder" valign="top" headers="mcps1.2.4.1.2 "><p id="p8593143812281"><a name="p8593143812281"></a><a name="p8593143812281"></a><a href="https://dl.fedoraproject.org/pub/epel/6/x86_64/" target="_blank" rel="noopener noreferrer">https://dl.fedoraproject.org/pub/epel/6/x86_64/</a></p>
    </td>
    </tr>
    </tbody>
    </table>

    6以上系列此处以CentOS 6.5 64位为例，执行以下命令安装Cloud-Init。

    **yum install https://dl.fedoraproject.org/pub/epel/6/x86\_64/epel-release-6-8.noarch.rpm**

    **yum install cloud-init**

-   **Fedora操作系统**

    安装Cloud-Init前，请确认操作系统已经配置好对应的网络安装源地址，请查看“/etc/yum.repo.d/fedora.repo”文件中是否已配置相关软件包安装源地址，如果没有配置相关地址源，请参考相关Fedora官网信息配置软件包安装源。

    执行以下命令，安装Cloud-Init。

    **yum install cloud-init**

-   **Debian和Ubuntu操作系统**

    安装Cloud-Init前，请确认操作系统已经配置好对应的网络安装源地址，请查看“/etc/apt/sources.list”文件中是否已配置相关软件包安装源地址，如果没有配置相关地址源，请参考Debian或者Ubuntu官网信息配置软件包安装源。

    执行以下命令，安装Cloud-Init。

    **apt-get update**

    **apt-get install cloud-init**


## 采用官方提供的cloud-init源码包通过pip方式安装Cloud-Init工具<a name="section124220553610"></a>

以cloud-init-0.7.9版本为例，Cloud-Init工具的安装步骤如下。

1.  下载cloud-init-0.7.9.tar.gz源码包（推荐优先选用0.7.9版本），上传到云服务器指定目录/home/下。

    cloud-init-0.7.9.tar.gz源码包下载地址：

    [https://launchpad.net/cloud-init/trunk/0.7.9/+download/cloud-init-0.7.9.tar.gz](https://launchpad.net/cloud-init/trunk/0.7.9/+download/cloud-init-0.7.9.tar.gz)

2.  在\~/.pip/目录下新建pip.conf文件，编辑内容如下。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >\~/.pip/若不存在，可使用命令**mkdir \~/.pip**命令新建。  

    \[global\]

    index-url  = https://<$mirror\>/simple/

    trusted-host = <$mirror\>

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >编辑内容中**<$mirror\>**部分可以选择公网PyPI源或教育网PyPI源进行替换。  
    >-   公网PyPI源：[https://pypi.python.org/](https://pypi.python.org/)  
    >-   教育网PyPI源：[https://pypi.tuna.tsinghua.edu.cn/](https://pypi.tuna.tsinghua.edu.cn/)  
    >    [https://pypi.mirrors.ustc.edu.cn/](https://pypi.mirrors.ustc.edu.cn/)  

3.  执行以下命令，安装本地下载的cloud-init源码包，安装过程中根据需要选择--upgrade参数。

    **\# pip install \[--upgrade\] /home/cloud-init-0.7.9.tar.gz**

4.  执行命令**cloud-init -v**，如回显信息如下表示安装Cloud-Init成功。

    ```
    cloud-init 0.7.9
    ```

5.  设置Cloud-Init相关服务为开机自启动。
    -   若操作系统是sysvinit自启动管理服务，则执行以下命令进行设置。

        **\# chkconfig --add cloud-init-local; chkconfig --add cloud-init; chkconfig --add cloud-config; chkconfig --add cloud-final**

        **\# chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

        **\# service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

    -   若操作系统是systemd自启动管理服务，则执行以下命令进行设置。

        **\# systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        **\# systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**



>![](public_sys-resources/icon-notice.gif) **注意：**   
>采用官方提供的Cloud-Init源码包通过pip方式进行安装时要注意以下两点。  
>1.  Cloud-Init安装时需要添加syslog用户到adm组。存在syslog用户直接添加syslog用户到adm组。不存在syslog用户（如Red Hat、CentOS和SUSE），执行下列命令创建syslog用户，添加到adm组：  
>    **useradd syslog**  
>    **groupadd adm**  
>2.  在/etc/cloud/cloud.cfg中system\_info部分的distro要根据具体操作系统发行版本做相应修改（如根据具体操作系统发行版相应修改为：**distro: ubuntu，distro: rhel，distro: sles，distro: debian, distro: fedora**）。  

## 采用源码编译安装方法****<a name="section14939636151511"></a>

由于Cloud-Init配置的相关内容已在源码包编译完成，执行以下操作步骤安装Cloud-Init成功即可，无需执行Cloud-Init配置操作。源码编译安装方法****的Cloud-Init工具Github开源地址：[https://github.com/huaweicloud/huaweicloud-cloud-init](https://github.com/huaweicloud/huaweicloud-cloud-init)

1.  执行以下命令，下载cloud-init压缩包，并将其复制至新建的/ tmp / CLOUD-INIT文件夹。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >0.7.6版本安装包下载地址：https://github.com/huaweicloud/huaweicloud-cloud-init/archive/cloud-init-0.7.6.zip  
    >0.7.9版本安装包下载地址：https://github.com/huaweicloud/huaweicloud-cloud-init/archive/cloud-init-0.7.9.zip  

    **wget https://github.com/huaweicloud/huaweicloud-cloud-init/archive/cloud-init-0.7.6.zip**

    **mkdir /tmp/CLOUD-INIT**

    **cp  **cloud-init-0.7.6.zip**  /tmp/CLOUD-INIT**

    **cd /tmp/CLOUD-INIT**

2.  执行如下命令，解压cloud-init压缩包。

    **unzip  **cloud-init-0.7.6.zip****

3.  执行如下命令进入cloud-init-0.7.6文件夹。

    **cd huaweicloud-cloud-init-**cloud-init**-0.7.6**

4.  按照操作系统类型，执行响应的命令安装cloud-init安装包。

    -   CentOS6.x/SUSE11.x：

        **python setup.py build**

        **python setup.py install --init-system sysvinit**

    -   CentOS7.x/SUSE12.x：

        **python setup.py build**

        **python setup.py install --init-system systemd**


    >![](public_sys-resources/icon-notice.gif) **注意：**   
    >Cloud-Init安装时需要添加syslog用户到adm组。存在syslog用户直接添加syslog用户到adm组。不存在syslog用户（如Red Hat、CentOS和SUSE），执行下列命令创建syslog用户，添加到adm组：  
    >**useradd syslog**  
    >**groupadd adm**  

5.  设置Cloud-Init相关服务为开机自启动。
    -   若操作系统是sysvinit自启动管理服务，则执行以下命令进行设置。

        **\# chkconfig --add cloud-init-local; chkconfig --add cloud-init; chkconfig --add cloud-config; chkconfig --add cloud-final**

        **\# chkconfig cloud-init-local on; chkconfig cloud-init on; chkconfig cloud-config on; chkconfig cloud-final on**

        **\# service cloud-init-local status; service cloud-init status; service cloud-config status; service cloud-final status**

    -   若操作系统是systemd自启动管理服务，则执行以下命令进行设置。

        **\# systemctl enable cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**

        **\# systemctl status cloud-init-local.service cloud-init.service cloud-config.service cloud-final.service**


6.  执行如下命令检查Cloud-Init是否安装成功。

    **cloud-init -v**

    **cloud-init init --local**

    回显信息如下所示表示安装Cloud-Init成功

    ```
    cloud-init 0.7.6
    ```


