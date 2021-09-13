# 准备镜像文件（Linux）<a name="ims_01_0209"></a>

您需要提前准备好符合条件的镜像文件，并了解操作系统的已知问题（参见[已知问题](已知问题.md)）。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   [表1](#table85212269215)中，文件系统、网络、驱动相关的配置需要在虚拟机内部完成，强烈建议您在原平台的虚拟机实施修改后，再导出镜像文件。当然，您也可以使用弹性云服务器完成这些配置，具体操作请参见“[Linux外部镜像文件在导出前未完成初始化配置，怎么办？](https://support.huaweicloud.com/ims_faq/ims_faq_0012.html)”。
>-   大文件导入（不超过1TB）目前仅支持RAW和ZVHD2格式，RAW镜像文件除了要满足[表1](#table85212269215)的要求外，还需要生成位表文件，同镜像文件一并上传。详细操作请参见[快速导入镜像文件](快速导入镜像文件.md)。

**表 1**  Linux操作系统的镜像文件限制

<a name="table85212269215"></a>
<table><thead align="left"><tr id="row853426172112"><th class="cellrowborder" valign="top" width="23.51%" id="mcps1.2.3.1.1"><p id="p12530269215"><a name="p12530269215"></a><a name="p12530269215"></a>镜像文件属性</p>
</th>
<th class="cellrowborder" valign="top" width="76.49000000000001%" id="mcps1.2.3.1.2"><p id="p1753152611212"><a name="p1753152611212"></a><a name="p1753152611212"></a>条件</p>
</th>
</tr>
</thead>
<tbody><tr id="row1453162692112"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p1253182672119"><a name="p1253182672119"></a><a name="p1253182672119"></a>操作系统</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><a name="ul889991962516"></a><a name="ul889991962516"></a><ul id="ul889991962516"><li>SUSE、Oracle Linux、Red Hat、Ubuntu、openSUSE、CentOS、Debian、Fedora、EulerOS、中标麒麟</li><li>支持32位和64位</li><li>操作系统不能与特定的硬件绑定</li><li>操作系统必须支持全虚拟化</li></ul>
<p id="p1787815142817"><a name="p1787815142817"></a><a name="p1787815142817"></a>所支持的操作系统版本请参考“<a href="https://support.huaweicloud.com/productdesc-ims/zh-cn_topic_0030713143.html" target="_blank" rel="noopener noreferrer">外部镜像文件支持的格式和操作系统类型</a>”，在此范围内的操作系统支持后台自动化配置（详情请参阅“<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0020.html" target="_blank" rel="noopener noreferrer">通过镜像文件注册私有镜像过程中，系统会对镜像做哪些修改？</a>”），在此之外的操作系统请您自行排查及安装virtio驱动，在注册镜像页面选择Other Linux，导入后系统启动情况取决于驱动完备度。</p>
</td>
</tr>
<tr id="row1653182610212"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p4532026152119"><a name="p4532026152119"></a><a name="p4532026152119"></a>镜像格式</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><p id="p17531426152112"><a name="p17531426152112"></a><a name="p17531426152112"></a>VMDK、VHD、QCOW2、RAW、VHDX、QED、VDI、QCOW、ZVHD2和ZVHD</p>
</td>
</tr>
<tr id="row15536261217"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p353142692117"><a name="p353142692117"></a><a name="p353142692117"></a>镜像大小</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><p id="p1498992571314"><a name="p1498992571314"></a><a name="p1498992571314"></a>镜像大小不超过128GB。</p>
<div class="p" id="p14410175834710"><a name="p14410175834710"></a><a name="p14410175834710"></a>如果镜像大小介于128GB和1TB之间，需要将镜像文件转换为RAW或ZVHD2格式，然后使用快速导入功能进行导入。<a name="ul16854182355610"></a><a name="ul16854182355610"></a><ul id="ul16854182355610"><li>参考“<a href="https://support.huaweicloud.com/bestpractice-ims/ims_bp_0052.html" target="_blank" rel="noopener noreferrer">通过qemu-img-hw工具转换镜像格式</a>”转换镜像格式。</li><li>参考“<a href="流程概览.md">快速导入镜像文件</a>”了解快速导入功能。</li></ul>
</div>
</td>
</tr>
<tr id="row3531626162117"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p35313261219"><a name="p35313261219"></a><a name="p35313261219"></a>网络能力</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><p id="p197299113553"><a name="p197299113553"></a><a name="p197299113553"></a><strong id="b1574020262166"><a name="b1574020262166"></a><a name="b1574020262166"></a>必选项，不设置会导致<span id="text128816242577"><a name="text128816242577"></a><a name="text128816242577"></a>云服务器</span><span id="text33022655711"><a name="text33022655711"></a><a name="text33022655711"></a></span>启动异常或网络能力异常，包括：</strong></p>
<a name="ul10942125439"></a><a name="ul10942125439"></a><ul id="ul10942125439"><li><a href="清理网络规则文件.md">清理网络规则文件</a></li><li><a href="设置网卡属性为DHCP（Linux）.md">设置网卡属性为DHCP</a></li></ul>
<p id="p1256214156553"><a name="p1256214156553"></a><a name="p1256214156553"></a><strong id="b33614309163"><a name="b33614309163"></a><a name="b33614309163"></a>可选项，即增值能力，主要包括：</strong></p>
<a name="ul1454250115714"></a><a name="ul1454250115714"></a><ul id="ul1454250115714"><li>开启网卡多队列<p id="p733615559471"><a name="p733615559471"></a><a name="p733615559471"></a>开启网卡多队列功能可以将网卡中断分散给不同的CPU处理，实现负载均衡，从而提升网络PPS和带宽性能。操作方法请参考“<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0030.html" target="_blank" rel="noopener noreferrer">如何设置镜像的网卡多队列属性</a>”。</p>
</li><li>配置动态获取IPv6地址<p id="p1340632184811"><a name="p1340632184811"></a><a name="p1340632184811"></a>IPv6的使用，可以有效弥补IPv4网络地址资源有限的问题。镜像中配置动态获取IPv6地址，发放的<span id="text8702194813582"><a name="text8702194813582"></a><a name="text8702194813582"></a>云服务器</span><span id="text1064845012583"><a name="text1064845012583"></a><a name="text1064845012583"></a></span>能够同时支持IPv4和IPv6地址。配置方法请参考“<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0046.html" target="_blank" rel="noopener noreferrer">如何开启云服务器动态获取IPv6</a>”。</p>
</li></ul>
</td>
</tr>
<tr id="row1558028151811"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p558018891810"><a name="p558018891810"></a><a name="p558018891810"></a>工具</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><p id="p1657443219185"><a name="p1657443219185"></a><a name="p1657443219185"></a>强烈建议安装Cloud-Init工具。</p>
<p id="p3276725102112"><a name="p3276725102112"></a><a name="p3276725102112"></a>Cloud-Init是开源的云初始化工具，使用安装了Cloud-Init的镜像创建<span id="text115710452232"><a name="text115710452232"></a><a name="text115710452232"></a>云服务器</span><span id="text715754522310"><a name="text715754522310"></a><a name="text715754522310"></a></span>时可以通过“用户数据注入”功能，注入初始化自定义信息（例如为<span id="text880054818234"><a name="text880054818234"></a><a name="text880054818234"></a>云服务器</span><span id="text780054816234"><a name="text780054816234"></a><a name="text780054816234"></a></span>设置登录密码）；还可以通过查询、使用元数据，对正在运行的<span id="text83201153142311"><a name="text83201153142311"></a><a name="text83201153142311"></a>云服务器</span><span id="text11320653132318"><a name="text11320653132318"></a><a name="text11320653132318"></a></span>进行配置和管理。不安装Cloud-Init工具，将无法对<span id="text1617155622311"><a name="text1617155622311"></a><a name="text1617155622311"></a>云服务器</span><span id="text61716568234"><a name="text61716568234"></a><a name="text61716568234"></a></span>进行自定义配置，只能使用镜像原有密码登录<span id="text1933535816239"><a name="text1933535816239"></a><a name="text1933535816239"></a>云服务器</span><span id="text8335258132315"><a name="text8335258132315"></a><a name="text8335258132315"></a></span>。</p>
<p id="p142251129111720"><a name="p142251129111720"></a><a name="p142251129111720"></a>安装方法请参考<a href="安装Cloud-Init工具.md">安装Cloud-Init工具</a>。</p>
</td>
</tr>
<tr id="row20361842182918"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p113644216291"><a name="p113644216291"></a><a name="p113644216291"></a>驱动</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><p id="p857214531434"><a name="p857214531434"></a><a name="p857214531434"></a><a href="安装原生的KVM驱动.md">安装原生的KVM驱动</a></p>
</td>
</tr>
<tr id="row7637883311"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p56591949191514"><a name="p56591949191514"></a><a name="p56591949191514"></a>文件系统</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><a name="ul6303717181618"></a><a name="ul6303717181618"></a><ul id="ul6303717181618"><li><a href="修改grub文件磁盘标识方式为UUID.md">修改grub文件磁盘标识方式为UUID</a></li><li><a href="修改fstab文件磁盘标识方式为UUID.md">修改fstab文件磁盘标识方式为UUID</a></li></ul>
</td>
</tr>
<tr id="row1661924212312"><td class="cellrowborder" valign="top" width="23.51%" headers="mcps1.2.3.1.1 "><p id="p196201042152313"><a name="p196201042152313"></a><a name="p196201042152313"></a>其他限制</p>
</td>
<td class="cellrowborder" valign="top" width="76.49000000000001%" headers="mcps1.2.3.1.2 "><a name="ul3863205042313"></a><a name="ul3863205042313"></a><ul id="ul3863205042313"><li>暂不支持创建带有数据盘的镜像，镜像文件中必须只能包含系统盘，且系统盘大小范围为：[40GB, 1024GB]</li><li>镜像文件的初始密码至少包含以下4种字符：大写字母、小写字母、数字、特殊字符（!@$%^-_=+[{}]:,./?）</li><li>镜像启动分区和系统分区必须包含在同一个磁盘中</li><li>支持的镜像引导方式：<p id="p1734688585"><a name="p1734688585"></a><a name="p1734688585"></a>x86架构部分操作系统镜像支持UEFI启动方式（<a href="https://support.huaweicloud.com/productdesc-ims/ims_01_0008.html" target="_blank" rel="noopener noreferrer">查看支持UEFI启动方式的操作系统</a>）。</p>
<p id="p736224481917"><a name="p736224481917"></a><a name="p736224481917"></a>ARM架构操作系统镜像仅支持UEFI启动方式。</p>
</li><li>镜像文件必须为非加密，否则可能导致镜像注册后创建的云服务器无法正常使用。</li><li>“/etc/fstab”文件中不能包含非系统盘的自动挂载信息，否则创建的<span id="text419153562410"><a name="text419153562410"></a><a name="text419153562410"></a>云服务器</span><span id="text141912358241"><a name="text141912358241"></a><a name="text141912358241"></a></span>可能无法正常登录。</li><li>如果外部镜像文件的系统盘为LVM设备，通过该镜像文件注册的私有镜像用来创建<span id="text74701445132415"><a name="text74701445132415"></a><a name="text74701445132415"></a>云服务器</span><span id="text7470745142418"><a name="text7470745142418"></a><a name="text7470745142418"></a></span>时，不支持文件注入。</li><li>外部镜像文件所在虚拟机如果经历了关机过程，则必须是优雅关机，否则使用私有镜像创建的<span id="text17974041924"><a name="text17974041924"></a><a name="text17974041924"></a></span><span id="text169748419214"><a name="text169748419214"></a><a name="text169748419214"></a>云服务器</span>在启动时可能会出现蓝屏。</li></ul>
</td>
</tr>
</tbody>
</table>

