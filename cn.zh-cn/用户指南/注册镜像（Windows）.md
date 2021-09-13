# 注册镜像（Windows）<a name="ims_01_0206"></a>

## 操作场景<a name="section717820315503"></a>

镜像文件上传到OBS桶以后，请参考本节指导注册镜像。

## 操作步骤<a name="section1753510552356"></a>

1.  登录IMS控制台。
    1.  登录管理控制台。
    2.  选择“计算 \> 镜像服务”。

        进入镜像服务页面。

2.  创建系统盘镜像。
    1.  单击右上角的“创建私有镜像”，进入创建私有镜像页面。
    2.  根据界面要求填写如下信息：

        包含“镜像类型和来源”和“配置信息”两个信息块，各参数说明参见[表1](#table050019474117)和[表2](#table6978715749)。

        **表 1**  镜像类型和来源

        <a name="table050019474117"></a>
        <table><thead align="left"><tr id="row1350164712110"><th class="cellrowborder" valign="top" width="25.96%" id="mcps1.2.3.1.1"><p id="p12501447314"><a name="p12501447314"></a><a name="p12501447314"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="74.03999999999999%" id="mcps1.2.3.1.2"><p id="p1350114720117"><a name="p1350114720117"></a><a name="p1350114720117"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row1450134714120"><td class="cellrowborder" valign="top" width="25.96%" headers="mcps1.2.3.1.1 "><p id="p1550114471116"><a name="p1550114471116"></a><a name="p1550114471116"></a>区域</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p1640415402364"><a name="p1640415402364"></a><a name="p1640415402364"></a>请选择靠近您业务的区域。</p>
        <p id="p05011247218"><a name="p05011247218"></a><a name="p05011247218"></a>如果区域选择错误，可以在私有镜像创建成功后通过“<a href="跨区域复制镜像.md">跨区域复制功能</a>”将镜像复制到其他区域。</p>
        </td>
        </tr>
        <tr id="row350214713113"><td class="cellrowborder" valign="top" width="25.96%" headers="mcps1.2.3.1.1 "><p id="p650294716116"><a name="p650294716116"></a><a name="p650294716116"></a>创建方式</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p75021947615"><a name="p75021947615"></a><a name="p75021947615"></a>选择“系统盘镜像”。</p>
        </td>
        </tr>
        <tr id="row1650284720113"><td class="cellrowborder" valign="top" width="25.96%" headers="mcps1.2.3.1.1 "><p id="p125022471113"><a name="p125022471113"></a><a name="p125022471113"></a>选择镜像源</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p850214712118"><a name="p850214712118"></a><a name="p850214712118"></a>选择“镜像文件”，然后从列表中选择保存镜像文件的桶，再选择对应的镜像文件。</p>
        </td>
        </tr>
        <tr id="row19047191220"><td class="cellrowborder" valign="top" width="25.96%" headers="mcps1.2.3.1.1 "><p id="p690516194212"><a name="p690516194212"></a><a name="p690516194212"></a>快速通道</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.03999999999999%" headers="mcps1.2.3.1.2 "><p id="p1139533015529"><a name="p1139533015529"></a><a name="p1139533015529"></a>可选参数，仅在选择zvhd2或raw格式的镜像文件时出现。</p>
        <p id="p690516196213"><a name="p690516196213"></a><a name="p690516196213"></a>快速通道功能可快速完成镜像制作，并且支持大文件上传（不超过1TB），但是镜像文件需要转换为zvhd2或raw格式并完成镜像优化。如果您已提前准备好符合要求的镜像文件，请勾选“开启快速通道”，然后勾选“镜像文件准备”后的确认信息。</p>
        <div class="note" id="note189513537562"><a name="note189513537562"></a><a name="note189513537562"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p9951353185614"><a name="p9951353185614"></a><a name="p9951353185614"></a>镜像文件格式转换、生成位表文件等操作请参考<a href="快速导入镜像文件.md">快速导入镜像文件</a>。</p>
        </div></div>
        </td>
        </tr>
        </tbody>
        </table>

        **表 2**  配置信息

        <a name="table6978715749"></a>
        <table><thead align="left"><tr id="row1597918159415"><th class="cellrowborder" valign="top" width="25.91%" id="mcps1.2.3.1.1"><p id="p597916152418"><a name="p597916152418"></a><a name="p597916152418"></a>参数</p>
        </th>
        <th class="cellrowborder" valign="top" width="74.09%" id="mcps1.2.3.1.2"><p id="p99796151642"><a name="p99796151642"></a><a name="p99796151642"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row2979615646"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p119791415146"><a name="p119791415146"></a><a name="p119791415146"></a>进行后台自动化配置</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p159799151641"><a name="p159799151641"></a><a name="p159799151641"></a>勾选后，后台系统将会对镜像文件进行相关检查及优化，具体包括哪些操作请参见“<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0020.html" target="_blank" rel="noopener noreferrer">通过镜像文件注册私有镜像过程中，系统会对镜像做哪些修改？</a>”。</p>
        </td>
        </tr>
        <tr id="row1597941514412"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p49796159415"><a name="p49796159415"></a><a name="p49796159415"></a>镜像用途</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p19791151244"><a name="p19791151244"></a><a name="p19791151244"></a>取值为“ECS系统盘镜像”和“BMS系统盘镜像”，表示此镜像用来创建弹性云服务器或裸金属服务器。本章节以选择“ECS系统盘镜像”为例。</p>
        </td>
        </tr>
        <tr id="row17257185463217"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p192581454163216"><a name="p192581454163216"></a><a name="p192581454163216"></a>架构类型</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p122581754203217"><a name="p122581754203217"></a><a name="p122581754203217"></a>根据待注册的镜像文件的架构类型，选择“x86”或“ARM”。</p>
        <a name="ul1613261511339"></a><a name="ul1613261511339"></a><ul id="ul1613261511339"><li>当系统识别的镜像文件架构类型与您设置的架构类型不一致时，以系统识别的架构类型为准。</li><li>当系统不能识别镜像文件的架构类型时，以您设置的架构类型为准。</li></ul>
        </td>
        </tr>
        <tr id="row1797901516417"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p297919150413"><a name="p297919150413"></a><a name="p297919150413"></a>启动方式</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p9438143331114"><a name="p9438143331114"></a><a name="p9438143331114"></a>可选参数，取值为“BIOS”和“UEFI”，两者的区别请参见“<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0049.html" target="_blank" rel="noopener noreferrer">UEFI启动方式与BIOS启动方式有哪些区别？</a>”。</p>
        <p id="p389711395713"><a name="p389711395713"></a><a name="p389711395713"></a>支持UEFI启动方式的操作系统版本请参见“<a href="https://support.huaweicloud.com/productdesc-ims/ims_01_0008.html" target="_blank" rel="noopener noreferrer">支持UEFI启动方式的操作系统版本</a>”。</p>
        <p id="p1697961514418"><a name="p1697961514418"></a><a name="p1697961514418"></a>此选项需用户确认待注册镜像文件本身的启动方式，并通过此选项告知云平台，以便于云平台完成镜像文件启动方式的相关配置。请选择正确的启动方式，否则，使用该镜像创建的<span id="text253746173815"><a name="text253746173815"></a><a name="text253746173815"></a>弹性云服务器</span><span id="text129595743815"><a name="text129595743815"></a><a name="text129595743815"></a></span>无法启动。</p>
        <div class="note" id="note19701013215"><a name="note19701013215"></a><a name="note19701013215"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p6702613415"><a name="p6702613415"></a><a name="p6702613415"></a>镜像文件为ARM架构类型时，仅支持UEFI启动方式。</p>
        </div></div>
        </td>
        </tr>
        <tr id="row5979161520418"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p397920159413"><a name="p397920159413"></a><a name="p397920159413"></a>操作系统</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p13980151519417"><a name="p13980151519417"></a><a name="p13980151519417"></a>为保证镜像的正常创建和使用，请确保选择的操作系统与镜像文件的操作系统类型一致。未选择时，系统会自动识别镜像文件的操作系统。</p>
        <div class="note" id="note1083205331415"><a name="note1083205331415"></a><a name="note1083205331415"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul183081759171412"></a><a name="ul183081759171412"></a><ul id="ul183081759171412"><li>系统识别的镜像文件操作系统与用户设置的操作系统不同时，以系统识别的操作系统为准。</li><li>系统不能识别镜像文件的操作系统时，以用户选择的操作系统为准。</li><li>用户选择或系统识别的镜像文件操作系统与实际不一致时，可能会对由此镜像文件最终创建的<span id="text94741046125720"><a name="text94741046125720"></a><a name="text94741046125720"></a>弹性云服务器</span><span id="text941354825714"><a name="text941354825714"></a><a name="text941354825714"></a></span>的性能产生影响。</li></ul>
        </div></div>
        </td>
        </tr>
        <tr id="row186599521354"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p5659125219510"><a name="p5659125219510"></a><a name="p5659125219510"></a>系统盘</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p165912527520"><a name="p165912527520"></a><a name="p165912527520"></a>设置系统盘容量，请确保输入的大小不小于源主机镜像文件的系统盘大小。</p>
        <div class="note" id="note106387506495"><a name="note106387506495"></a><a name="note106387506495"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p263819508495"><a name="p263819508495"></a><a name="p263819508495"></a>如果上传使用vhd格式的镜像是通过qemu-img或者其他工具转换生成的，设置系统盘容量时请参考<a href="https://support.huaweicloud.com/ims_faq/ims_faq_0103.html" target="_blank" rel="noopener noreferrer">为什么VHD格式的镜像上传失败，任务中心查看报错为外部镜像文件的系统盘容量大于用户设置的系统磁盘容量？</a>进行检查。</p>
        </div></div>
        </td>
        </tr>
        <tr id="row377757316"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p67771871416"><a name="p67771871416"></a><a name="p67771871416"></a>数据盘</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p1120437113116"><a name="p1120437113116"></a><a name="p1120437113116"></a>您还可以增加多块数据盘随系统盘镜像一起创建，需要事先制作好数据盘镜像文件。该功能一般适用于将其他平台的虚拟机及其数据盘一起迁移至本平台。</p>
        <p id="p1177707712"><a name="p1177707712"></a><a name="p1177707712"></a>操作方法：单击<a name="image0700648174816"></a><a name="image0700648174816"></a><span><img id="image0700648174816" src="figures/Image-4.png"></span>图标增加一块数据盘，设置数据盘容量，然后单击“选择镜像文件”，从列表中先选择保存镜像文件的桶，再选择对应的数据盘镜像文件。</p>
        <p id="p2055712561176"><a name="p2055712561176"></a><a name="p2055712561176"></a>最多添加3块数据盘。</p>
        </td>
        </tr>
        <tr id="row36593522511"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p19659452051"><a name="p19659452051"></a><a name="p19659452051"></a>名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p126597521359"><a name="p126597521359"></a><a name="p126597521359"></a>设置一个便于您识别的镜像名称。</p>
        </td>
        </tr>
        <tr id="row66596520512"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p156591952159"><a name="p156591952159"></a><a name="p156591952159"></a>加密</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p936015584547"><a name="p936015584547"></a><a name="p936015584547"></a>可选参数，如果需要加密镜像，请勾选“KMS加密”并从密钥列表中选择需要使用的密钥名称。勾选“KMS加密”后，系统会为用户创建默认主密钥“ims/default”。您也可以从密钥列表中选择需要使用的密钥名称。</p>
        <p id="p96591652653"><a name="p96591652653"></a><a name="p96591652653"></a>加密镜像详情请参考<a href="创建加密镜像.md">创建加密镜像</a>。</p>
        </td>
        </tr>
        <tr id="row1320515143611"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p112050141866"><a name="p112050141866"></a><a name="p112050141866"></a>企业项目</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p1920521419610"><a name="p1920521419610"></a><a name="p1920521419610"></a>从下拉列表中选择所在的企业项目。该参数针对企业用户使用，只有开通了企业项目的客户，或者权限为企业主帐号的客户才可见。</p>
        <p id="p1916781617248"><a name="p1916781617248"></a><a name="p1916781617248"></a>企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。</p>
        </td>
        </tr>
        <tr id="row142057141619"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p1420612141267"><a name="p1420612141267"></a><a name="p1420612141267"></a>标签</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p820611415612"><a name="p820611415612"></a><a name="p820611415612"></a>可选参数，为镜像设置标签键和标签值，便于识别和管理。</p>
        </td>
        </tr>
        <tr id="row720613141962"><td class="cellrowborder" valign="top" width="25.91%" headers="mcps1.2.3.1.1 "><p id="p7206111416617"><a name="p7206111416617"></a><a name="p7206111416617"></a>描述</p>
        </td>
        <td class="cellrowborder" valign="top" width="74.09%" headers="mcps1.2.3.1.2 "><p id="p420631410613"><a name="p420631410613"></a><a name="p420631410613"></a>可选参数，对镜像进行描述。</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  单击“立即创建”，根据界面提示，确认镜像规格。阅读并勾选《镜像制作承诺书》和《华为镜像免责声明》，单击“提交申请”。

3.  返回私有镜像列表，等待镜像状态变为“正常”，注册成功。

    如果在创建过程中添加了数据盘，将同时生成系统盘镜像和数据盘镜像，数据盘镜像个数由您所添加的数据盘数量而定，不超过3个。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >根据镜像文件大小不同，将镜像文件注册为私有镜像所使用的时间不同，请耐心等待。


