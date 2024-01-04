停车场管理_充电桩_停车收费_物业管理_物联网_自助缴费 （最新版本：2023年11月21日发布，几乎每天都更新）

【严正声明】： 本项目基础代码完整，喜欢的个人爱好者自行克隆代码，项目能跑起来，在此基础框架开发至少能省你6-12个月时间，此项目为商业代码，项目代码已经完全开放，请勿混淆，感谢理解和支持，在不影响原来收费客户前提下开源

【声明】：本项目里面的代码没有任何私jar包，本来就是开源项目，代码没有丢包或者故意丢代码导致项目报错的情况，但是不保证能商用，个人拿来作为入门研究和快速二次开发是个不错的选择，想要商用的建议自己进行二次开发。这项目代码肯定能跑起来，基础太差的小白，自己先去学习学习java基础和springboot基础！

【商业合作】：如果你自己运行和或者二次开发本系统有压力，或者不想花太多精力，也可以联系作者我个人，微信:Dove981011512,单次收费2万起步，开源代码已经是全代码的，如非必要请勿加，感谢您的海涵，再次跟您说声抱歉和感谢。

详细在线介绍和部署文档,测试地址【推荐仔细查阅】:
这个版本是V2.0，如果感兴趣，可以查看我们3.0

【V3.0】: https://www.showdoc.com.cn/2192066741521376/10290721898432961

【开发建议】：想研究相机对接的，建议自己买个开发机器，连个两三百的开发机器你都没有，不要谈啥研究车牌识别系统。先声明，我自己不是推销产品啥的，根据个人需求，需要购买的自己去某宝购买，

前端小程序开源地址(2.0)：https://gitee.com/wangdefu/parking_system_applet

前端小程序开源地址(3.0)：https://gitee.com/gebixiaowangzi/cfzhv3.0

后台管理开源地址(3.0)：https://gitee.com/gebixiaowangzi/cfzhv3.0_public_admin

【我们的优势】：最近我们新增了充电桩功能模块，物业系统，人脸门禁，上门报修，准备更新开源版，欢迎大家体验

【注意】：一定要先配置 oauth2的公私密钥对，放到admin目录下，对应数据库记得配置对应的用户账号和密码，代码里面我有备注。如果连oauth2都玩不转的，建议你放弃，感谢您的海涵。

【功能介绍】： ①本停车场系统兼容市面上主流的多家相机，理论上兼容所有硬件，可灵活扩展，②相机识别后数据自动上传到云端并记录，校验相机唯一id和硬件序列号，防止非法数据录入，③用户手机查询停车记录详情可自主缴费(支持微信，支付宝，银行接口支付，支持每个停车场指定不同的商户进行收款)，支付后出场在免费时间内会自动抬杆。④支持app上查询附近停车场(导航，可用车位数，停车场费用，优惠券，评分，评论等)，可预约车位。⑤断电断网支持岗亭人员使用app可接管硬件进行停车记录的录入。

【技术架构】： 后端开发语言java，采用最新springcloudalibaba版本开发，框架oauth2+springboot2.6(可升级到3.0)+doubble3.2，使用nacos, seata，sentinel，，数据库mysql/mongodb/redis/可追加oceanbase和tidb超大型数据库，即时通讯底层框架netty4，安卓和ios均为原生开发，后台管理模板vue-typescript-admin-template,文件服务fastDFS/minio/阿里云oss/七牛云，短信目前仅集成阿里云短信服务。为百亿级数据而生，千万级用户无忧，目前真实用户1000w无压力，大数据时代物联网必备

【开源情况】： 代码完全开源，不存在授权问题，完全自主原创，不存在任何后门，不使用任何第三方私有jar包，性能和安全完全自主可控，想怎么耍就这么耍，就是这么任性，后续更新的话本人会持续更新部署教程。代码专业规范，新手看得懂，高手喜欢用。本系统完全免费

【部署环境】： 目前仅测试linux环境一切正常，win环境没部署过，演示地址在本文章末尾

【关于作者】： 屌丝码农一枚，6年前曾就职于开发停车场系统的公司，发现目前国内该领域垄断，技术过于陈旧，没有一个规范，故个人用来接近3年的时间在业余时间开发出这种系统，现代化标准的互联网应用，定位大型物联网大数据云平台系统，我个人微信Dove981011512，如果你在部署我这套系统中遇到问题或者发现存在漏洞的请联系我，存在不足之处还望多多提宝贵意见，让我们打破市场垄断，让物联网应用更好的服务生活社会

软件架构 一、技术构成简述 （一）编程语言与架构简述 1．开发语言 （1）服务端 服务端语言目前均采用java语言开发，jdk版本要求1.8+。开发框架为springboot2+dubbo，鉴权采用oauth2，DB操作框架Mybaits，即时通讯底层框架与协议netty4

（2）客户端 目前我们主要客户端分为三个场景，分别为安卓，ios，微信公众号。安卓与ios均为原生开发，H5页面web端框架为vue

（3）后台管理 后台管理前端框架采用的是主流的vue element admin(TypeScript版本)，分层清晰，官方文档完整，社区活跃

2．数据存储 （1）重要数据存储 重要数据均采用mysql进行存储（可以增加支持oceanbase，支持百亿级大数据），支持部署主从，大部分数据尽可能进行事务处理，确保数据容灾性

（2）一般数据存储 非重要性数据例如聊天内容，系统消息通知，广告等数据均存储于mongodb数据库中

（3）缓存数据存储 微小量缓存会存在mysql中，例如评论的前N条评论快照会超小量进行字段适当冗余，在提高存储性价比情况下大大提高数据的查询能力。其它大部分数据缓存均存储于redis数据中

3．性能与安全 （1）性能解决方案 架构与技术解决方案均为本团队一线5年开发经验总结，目前我们正在接触的项目真实用户40w+，毫无压力，我们系统采用的架构与技术均在仔细多方面综合考虑后多次调整，采用更加合理，性能更佳的模式与解决方案

（2）安全解决方案 所有请求均需携带jwt串token进行访问，每个接口服务和管理服务均需配置公钥文件且具有jwt串token合法性校验能力，用户权限服务携带私钥文件负责密钥生成

4．架构与生命力 （1）采用架构 本系统采用阿里巴巴微服务框架dubbo来进行实现微服务提供能力，追求高性能，高可用，超细粒度独立微服务，相同服务可以动态灵活增加与减少，支持不停机发布新版本服务。每个服务之间均为独立存在，互不影响。例如短信发送，支付，订单，停车场系统接口，停车场后台管理，停车场提供者服务等均为独立的服务。

（2）架构潜力 整个系统众多服务分工明确，细粒度微服务，实现真正的插拔服务，功能的删减或停用，新增等均可在不破坏和入侵原来系统的前提下满足新的开发需求

5．二次开发说明 （1）适用客户对象 ①本身有互联网it编程技术和经验或者拥有技术团队的。 ②不具备第一个条件但是费用预算比较充足，二次开发需求少或者愿意支付高额定制费的 （2）团队要求 服务器运维，安卓与ios开发者，web前端开发者，java实际开发经验2年+开发者

（3）技术要求 过硬的java编程能力，网络编程能力，数据库设计与优化能力，架构设计能力，微服务思维能力，成熟的前端技术开发能力，中大型系统部署与运营能力

（4）硬件要求 Linux操作系统，8核16G(最低)5M带宽，可多台服务器中的微服务指向统一微服务调度中心(本系统微服务调度中心管理平台zookeeper)

（二）软件与硬件数据交互简述 1．硬件端 （1）目前解决方案 封装工具类，兼容市场主流硬件设备，只负责各类硬件数据封装为统一数据结构。硬件发包目前多为http主动推送数据，被动接受服务端返回指令

（2）未来解决方案 改造主流厂商硬件底层服务系统，新增硬件规范的合法身份数据，采用长连接进行数据交互，保证数据与指令的实时性与可靠性得到更好的保障

2．服务端 （1）被动处理硬件数据 中间件处理各类前端数据，接收硬件推送数据，解析，计算，做出相应反馈

（2）主动通知硬件发生事件行为 长连接推送指令，例如开闸，实时动态配置硬件数据等，

二、常规功能简述 （一）基础功能 1．硬件管理 支持单个硬件管理与记录，硬件在线状态，维修与进度记录等。与指定停车场出入口进行绑定，均有记录GPS位置

2．停车场管理 不同时段费用配置，每日封顶因素综合参与动态计费，也支持静态+每日上限计费。支持查询附近停车场功能

3．停车记录管理 详细记录产生时间，地点，进出口位置，进出时间，异常数据实时推送与快速处理

4．支付机构管理 每个停车场的支付账号均可以独立配置，支持同一个停车场使用多家支付机构进行支付，例如支付宝，微信，银联等。

5．支付与优惠活动管理 支付宝与微信，银联都均支持免密支付(无感支付)。本系统自带优惠券功能，支持支持多种套餐自定义与用户进行快捷手机上下单随时购买

（二）特色功能 1．异常数据实时推送，汇报，及时处理，提前预知与通知 2．即时通讯功能(IM聊天沟通) 性能，架构，优化等均参考微信聊天功能机制进行开发

3．行业好友与圈子 让该应用不止只能停车，还能交到志同道合的行业知音，让应用更有温度

4．商城与营销功能 此功能主要考虑到使用者有运营周边的兴趣和能力，在商城和广告营销上进行盈利

安装教程 安装JDK1.8+ 安装MySQL5.6+ 安装MongoDB 安装Redis 安装FastDFS 安装Zookeeper 将打包好的代码上传到服务器上，直接运行jar包即可 详细安装教程文档地址 使用说明(swagger2文档) 国内领先水平 专业演示 旧版本(V2.0)演示地址已经停止, 最新版本是(V3.0),V3.0上面已经给APP和演示地址了 如果您发现有代码有什么不足之处请跟我留言，如果我留言不及时请加我个人微信Dove981011512(学生搞啥论文的以及个人小白不要加我，暂时没时间和精力帮忙，还望您见谅和理解)
