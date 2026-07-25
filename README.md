# 想用 VPS 搭 WordPress？这份狗云全套餐实测指南，帮你避开 90% 的踩坑

很多人第一次搜 "VPS for WordPress"，脑子里其实是糊涂的。你大概知道共享主机便宜但慢，知道 WordPress 托管贵得离谱，听说 VPS 是性价比之选，可一打开各家官网，1 核 1G、2 核 4G、NVMe、BGP、CN2 一堆词砸过来，瞬间就懵了。我之前帮朋友迁移一个日访 2000 的小博客，光是选配置就纠结了三天，最后发现真正难的不是技术，是没人把"什么站点该买什么 VPS"这件事讲明白。

这篇文章就想把这事讲明白。主角是狗云（DogYun），一家 2019 年成立、主打香港和亚太节点的中文云服务商。我会拿它的全部套餐做个横向对比，告诉你 WordPress 站点到底该怎么挑。不堆术语，只说人话。

## WordPress 对 VPS 到底有什么要求

先把底层逻辑理清楚。WordPress 本身是个 PHP + MySQL 的应用，跑起来需要 Web 服务器（Nginx 或 Apache）、数据库、PHP 解释器三件套，业内俗称 LNMP。

**最低能跑的配置**：理论上 512MB 内存就能装，1 核 1G 是底线。但底线意味着你装完插件、跑几个页面就开始捉襟见肘。

**舒服的配置**：2 核 2GB 起步，配 40GB 以上 SSD。这个档位跑 WordPress + WooCommerce 这种电商站，配合缓存插件，日访几千毫无压力。

**进阶配置**：4 核 4GB 以上，适合多站点、会员系统、LMS 课程站这类重应用。

另外一个常被忽略的点：**带宽和流量**。WordPress 站点图片多，一篇文章配 5 张图每张 300KB，单次访问轻松消耗 2MB 流量。月流量 500GB 看着多，真到日访 5000 的时候也就见底了。所以选套餐别只盯 CPU 内存，流量池大小同样关键。

## 为什么聊聊狗云这家

国内搜 "VPS for WordPress" 出来的结果，基本都是 Bluehost、Hostinger、ScalaHosting 这些海外英文主机商。它们当然能跑 WordPress，但对中文站点有个硬伤——节点远、延迟高、回程绕路。

狗云不一样。它 2019 年从老牌虚拟主机业务里独立出来，专注香港和亚太节点，自营香港机房接入 HKIX、EIE、TPIX、NTT、HE、Telstra、Retn、Cogent、GSL 等十余条线路，精品路线还带 CN2+CU+CMI 三网优化。对中文用户来说，香港节点延迟通常 30-50ms，比美国节点动辄 180ms+ 体验好得多。

它三条产品线分得清清楚楚：

- **弹性云服务器**：KVM 虚拟化，配置随时升降，按小时计费，适合动态需求
- **经典云服务器**：固定配置包年包月，价格最低 10 元/月，适合稳定建站
- **独立物理服务器**：独享整机，最低 400 元/月，适合大流量站

下面重点讲讲前两个，因为搭 WordPress 90% 的人会在这两条线里选。

## 数据中心怎么选：先看你的访客在哪

狗云的节点不少，但不是每个都适合 WordPress。我帮你按场景归类：

| 节点 | 适用场景 | 备注 |
|------|---------|------|
| 香港-KC | 中文站点首选，CN2+CU+CMI 精品路线 | 可附加高防 IP |
| 香港-MG | 大带宽高配，适合图片/视频站 | 1Gbps 带宽 |
| 香港-CLD | 老牌机房性价比高，预算有限选它 | 50-100Mbps |
| 韩国 | 备选亚太节点，多线路 BGP 优化 | 延迟略高于香港 |
| 日本-DC2 | 大阪 BGP 路线，适合日韩访客 | 50Mbps |
| 美国-LA | 英文站、海外访客为主，带 20G 防御 | 100Mbps |
| 重庆 | 国内备案站，联通骨干接入 | 需要备案 |

**一句话原则**：访客在中国大陆，选香港-KC 或香港-CLD；访客在海外，选美国-LA；纯英文站且预算敏感，韩国节点也是个备选。

## 弹性云 vs 经典云：WordPress 该选哪个

这俩长得像，脾气完全不同。

**弹性云**是按需付费的"云"模式。你今天编译软件需要 8 核，明天跑完降回 1 核，配置随时改，按小时扣费。还有"机龄计划"——用得越久送的流量越多，累计 12 个月每月流量上限能翻到 468GB。对 WordPress 来说，弹性云适合这些场景：

- 站点流量波动大，大促时临时升配
- 测试环境用完就销毁，预付费可退
- 不确定未来配置需求，想先小后大

**经典云**是传统包年包月的"VPS"模式。固定配置固定价，开通后不能改型号，但胜在价格低、续费不涨价。香港特惠套餐年付 150 元起，折合每月 12.5 元，是整个平台最便宜的 WordPress 落地方案。适合：

- 配置需求明确的稳定博客
- 不想折腾升降配的个人站长
- 预算敏感、追求长期低价

**我的建议**：刚起步的 WordPress 站，先用经典云特惠套餐跑半年，等流量上来了再迁移到弹性云。狗云支持自助销毁退款，迁移成本不高。

## 全套餐对比：一张表看完所有选择

这是本文重点。我把狗云官网在售的全部套餐整理成表，覆盖弹性云、经典云、独立服务器三大产品线。购买链接都带 AFF 追踪参数，直接点击即可下单。

### 经典云服务器（适合大多数 WordPress 站点）

| 套餐 | 位置 | CPU | 内存 | 硬盘 | 带宽 | 月流量 | 价格 | 购买 |
|------|------|-----|------|------|------|--------|------|------|
| hk.kc.s | 香港-KC | 1 核 EPYC 7003 | 1GB | 20GB SSD | 25Mbps | 250GB | ¥35/月（年付 ¥350） |  [立即购买](https://vm.dogyun.com/server/create/141?ref=vipgo) |
| hk.kc.m | 香港-KC | 2 核 EPYC 7003 | 2GB | 40GB SSD | 30Mbps | 500GB | ¥60/月（年付 ¥600） |  [立即购买](https://vm.dogyun.com/server/create/136?ref=vipgo) |
| hk.kc.xm | 香港-KC | 2 核 EPYC 7003 | 4GB | 60GB SSD | 35Mbps | 750GB | ¥90/月（年付 ¥900） |  [立即购买](https://vm.dogyun.com/server/create/137?ref=vipgo) |
| hk.kc.l | 香港-KC | 4 核 EPYC 7003 | 4GB | 80GB SSD | 40Mbps | 1000GB | ¥100/月（年付 ¥1000） |  [立即购买](https://vm.dogyun.com/server/create/138?ref=vipgo) |
| hk.kc.xl | 香港-KC | 4 核 EPYC 7003 | 8GB | 120GB SSD | 45Mbps | 1500GB | ¥150/月（年付 ¥1500） |  [立即购买](https://vm.dogyun.com/server/create/139?ref=vipgo) |
| hk.kc.xxl | 香港-KC | 8 核 EPYC 7003 | 8GB | 160GB SSD | 50Mbps | 2000GB | ¥180/月（年付 ¥1800） |  [立即购买](https://vm.dogyun.com/server/create/140?ref=vipgo) |
| hk.kc.xxxl | 香港-KC | 8 核 EPYC 7003 | 16GB | 240GB SSD | 50Mbps | 3000GB | ¥260/月（年付 ¥2600） |  [立即购买](https://vm.dogyun.com/server/create/142?ref=vipgo) |
| hk.cld.s | 香港-CLD | 1 核 Xeon E5 | 1GB | 20GB SSD | 50Mbps | 300GB | ¥25/月（年付 ¥250） |  [立即购买](https://vm.dogyun.com/server/create/36?ref=vipgo) |
| hk.cld.m | 香港-CLD | 1 核 Xeon E5 | 1GB | 30GB SSD | 60Mbps | 500GB | ¥35/月（年付 ¥350） |  [立即购买](https://vm.dogyun.com/server/create/55?ref=vipgo) |
| hk.cld.l | 香港-CLD | 1 核 Xeon E5 | 2GB | 40GB SSD | 70Mbps | 800GB | ¥50/月（年付 ¥500） |  [立即购买](https://vm.dogyun.com/server/create/38?ref=vipgo) |
| hk.high.s | 香港-CLD 高配 | 2 核 EPYC 7003 | 4GB | 60GB SSD | 80Mbps | 1000GB | ¥80/月（年付 ¥800） |  [立即购买](https://vm.dogyun.com/server/create/52?ref=vipgo) |
| hk.high.m | 香港-CLD 高配 | 4 核 EPYC 7003 | 8GB | 120GB SSD | 80Mbps | 2000GB | ¥150/月（年付 ¥1500） |  [立即购买](https://vm.dogyun.com/server/create/53?ref=vipgo) |
| hk.high.l | 香港-CLD 高配 | 8 核 EPYC 7003 | 16GB | 180GB SSD | 80Mbps | 3000GB | ¥250/月（年付 ¥2500） |  [立即购买](https://vm.dogyun.com/server/create/54?ref=vipgo) |
| hk.mini | 香港特惠 | 1 核 Xeon E5 | 0.75GB | 15GB SSD | 30Mbps | 500GB | ¥150/年 |  [立即购买](https://vm.dogyun.com/server/create/83?ref=vipgo) |
| hk.small | 香港特惠 | 1 核 Xeon E5 | 1GB | 25GB SSD | 30Mbps | 1024GB | ¥276/年 |  [立即购买](https://vm.dogyun.com/server/create/39?ref=vipgo) |
| hk.medium | 香港特惠 | 1 核 Xeon E5 | 2GB | 50GB SSD | 30Mbps | 2048GB | ¥396/年 |  [立即购买](https://vm.dogyun.com/server/create/40?ref=vipgo) |
| hk.large | 香港特惠 | 2 核 EPYC 7003 | 4GB | 80GB SSD | 30Mbps | 3072GB | ¥780/年 |  [立即购买](https://vm.dogyun.com/server/create/41?ref=vipgo) |
| hk.st.s | 香港大盘 | 1 核 Xeon Platinum | 1GB | 250GB | 1000Mbps | 5000GB | ¥40/月（年付 ¥400） |  [立即购买](https://vm.dogyun.com/server/create/150?ref=vipgo) |
| hk.st.m | 香港大盘 | 2 核 Xeon Platinum | 2GB | 500GB | 2000Mbps | 10000GB | ¥80/月（年付 ¥800） |  [立即购买](https://vm.dogyun.com/server/create/151?ref=vipgo) |
| hk.st.l | 香港大盘 | 4 核 Xeon Platinum | 4GB | 1000GB | 3500Mbps | 20000GB | ¥140/月（年付 ¥1400） |  [立即购买](https://vm.dogyun.com/server/create/152?ref=vipgo) |
| hk.st.xl | 香港大盘 | 8 核 Xeon Platinum | 8GB | 2000GB | 5000Mbps | 40000GB | ¥260/月（年付 ¥2600） |  [立即购买](https://vm.dogyun.com/server/create/153?ref=vipgo) |
| la.tu2.s | 美国-LA | 1 核 | 1GB | 20GB | 50Mbps | 500GB | ¥30/月 |  [立即购买](https://vm.dogyun.com/server/create/24?ref=vipgo) |
| la.tu2.m | 美国-LA | 1 核 | 1GB | 30GB | 100Mbps | 1000GB | ¥45/月 |  [立即购买](https://vm.dogyun.com/server/create/25?ref=vipgo) |
| la.tu2.l | 美国-LA | 2 核 | 2GB | 40GB | 200Mbps | 2000GB | ¥80/月 |  [立即购买](https://vm.dogyun.com/server/create/26?ref=vipgo) |
| cq.v6.a | 重庆 v6 | 1 核 | 1GB | 20GB | 25Mbps | 300GB | ¥30/季（年付 ¥100） |  [立即购买](https://vm.dogyun.com/server/create/90?ref=vipgo) |
| cq.v6.b | 重庆 v6 | 1 核 | 2GB | 40GB | 25Mbps | 500GB | ¥45/季（年付 ¥150） |  [立即购买](https://vm.dogyun.com/server/create/91?ref=vipgo) |
| cq.v6.c | 重庆 v6 | 2 核 | 4GB | 60GB | 50Mbps | 1000GB | ¥30/月（年付 ¥300） |  [立即购买](https://vm.dogyun.com/server/create/92?ref=vipgo) |

> 说明：香港-MG、日本 CMI、韩国、重庆联通等套餐当前官网显示售罄，不在上表列出。需要时可关注 👉 [狗云官网](https://bit.ly/Dogyun) 补货通知。

### 弹性云服务器（按需付费，配置灵活）

弹性云采用按小时计费 + 月度封顶模式，价格随数据中心和资源动态变化。下面是各节点 1 核 2GB 起步配置的参考月费：

| 数据中心 | 起步配置 | 带宽 | 起步月费 | 购买入口 |
|---------|---------|------|---------|---------|
| 香港-KC | 1-8 核 / 2-16GB / 20-240GB | 50Mbps | ¥33.12/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 香港-MG | 1-8 核 / 2-16GB / 20-100GB | 1000Mbps | ¥34.92/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 香港-CLD | 1-8 核 / 2-16GB / 20-100GB | 100Mbps | ¥31.32/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 韩国 | 1-8 核 / 2-16GB / 20-80GB | 50Mbps | ¥33.84/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 日本-DC2 | 1-8 核 / 2-16GB / 20-80GB | 50Mbps | ¥35.28/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 美国-LA | 1-8 核 / 2-16GB / 20-80GB | 100Mbps | ¥39.60/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |
| 重庆 | 2-16 核 / 4-32GB / 40-240GB | 100Mbps | ¥34.92/月起 |  [立即创建](https://cvm.dogyun.com/server/create?ref=vipgo) |

弹性云的好处是配置随时调，月费封顶。比如你选 2 核 4GB 跑 WordPress，平时月费大概 60-80 元，需要编译大文件时临时拉到 8 核，用几小时降回去，按小时补差价。

### 独立物理服务器（大流量站点首选）

如果你的 WordPress 站已经做到日均 PV 5 万以上，或者跑 WooCommerce 大型商城，虚拟化 VPS 的 CPU 和 IO 限制会成为瓶颈，这时候考虑独立服务器。狗云几款主力机型：

| 型号 | 位置 | CPU | 内存 | 存储 | 价格 | 购买 |
|------|------|-----|------|------|------|------|
| HK.KC.M.S | 香港-KC | Xeon E5-2630 V2 6C12T | 32GB DDR3 | 480GB SSD | ¥400/月（年付 ¥4000） |  [立即购买](https://ds.dogyun.com/server/create?ref=vipgo) |
| CQ.A | 重庆 | Xeon E5-2630 v4 10C20T | 64GB DDR4 | 800GB SSD | ¥400/月（年付 ¥4000） |  [立即购买](https://ds.dogyun.com/server/create?ref=vipgo) |
| HK.KC.L.2S | 香港-KC | 2×Xeon Gold 6148 40C80T | 64GB DDR4 | 960GB SSD | ¥950/月（年付 ¥9500） |  [立即购买](https://ds.dogyun.com/server/create?ref=vipgo) |
| HK.KC.L.3M | 香港-KC | 2×Xeon Gold 6248 40C80T | 128GB DDR4 | 960GB NVMe | ¥1100/月（年付 ¥11000） |  [立即购买](https://ds.dogyun.com/server/create?ref=vipgo) |

独立服务器年付送两个月，且高速流量可结转到次月，对图片多的 WordPress 站很友好。

## 优惠码与最新活动：下单前先看这

狗云常年有折扣码，叠加下来能省不少。当前有效的几个：

**常规折扣码**

- **`丙午`**：新开弹性云 7 折，新开经典云（特价机除外）8 折，续费同价
- **`2026`**：与"丙午"同效，弹性云 7 折、经典云 8 折
- **`jian100`**：新开独立物理服务器立减 100 元

**七周年促销（2026 年 7 月 21 日 - 7 月 27 日）**

1. 单笔充值每满 100 元送 10 元
2. 幸运大转盘每日抽奖，奖品含 5 折码、流量包、余额
3. LV2 及以上用户免费随机续期一台经典云（最高三个月）；LV1 用户免费领弹性云通用流量包（最高 600G）

下单流程：进入 👉 [狗云控制台](https://bit.ly/Dogyun) → 充值 → 选择套餐 → 结算页输入优惠码 → 完成支付。

**提醒**：特价套餐（如 HK.MINI、香港 EQ 系列）属于限时限量特供，不参与优惠码折扣，但本身价格已经压到最低，香港 VPS 年付不到 200 元，续费还不涨价。

## WordPress 部署实操：从开机到上线

VPS 买下来只是第一步，真正让 WordPress 跑起来还有几道工序。我按最简路径讲：

**第一步：选系统**

狗云控制台支持一键重装，推荐 Debian 12 或 Ubuntu 22.04，社区文档多、问题好搜。CentOS 已停止维护，新手别选。

**第二步：装 LNMP 环境**

两条路：

- **宝塔面板**：执行一行安装命令，5 分钟出可视化面板，软件商店一键装 Nginx + MySQL 8 + PHP 8.2，适合新手
- **LNMP 一键脚本**：命令行安装，资源占用更小，1GB 内存机器首选

**第三步：建站**

宝塔里点"网站 → 添加站点"，填域名、选 PHP 版本，上传 WordPress 安装包到根目录，浏览器访问域名按向导走完即可。

**第四步：域名解析**

在域名服务商处添加 A 记录，指向 VPS 的 IPv4 地址。如果选了香港节点，DNS 生效通常几分钟内完成。

**第五步：装 SSL**

宝塔面板一键申请 Let's Encrypt 免费证书，自动续期。WordPress 后台"设置 → 常规"把站点地址改成 https:// 开头。

整个过程熟练的话半小时搞定。卡壳的点通常在防火墙放行端口，记得宝塔和云控制台两处都要放行 80 和 443。

## 性能优化：让 WordPress 真正跑出 VPS 的速度

很多人买完 VPS 装 WordPress，发现速度还不如共享主机，原因九成在没做缓存。VPS 给了你资源，但 WordPress 默认每访问一次就查一次数据库，再快的 CPU 也扛不住。

**必备优化项**

1. **页面缓存**：装 WP Super Cache 或 W3 Total Cache，把动态页面静态化，访问速度能提升 5-10 倍
2. **对象缓存**：内存够的话装 Redis 或 Memcached，缓存数据库查询结果
3. **PHP 调优**：开启 OPcache，调整 `memory_limit` 到 512MB，`max_execution_time` 调到 300
4. **图片压缩**：装 ShortPixel 或 Imagify，自动压缩上传的图片
5. **CDN 加速**：接 Cloudflare 免费版，静态资源走边缘节点，回源压力骤减

**资源分配建议**

| 站点类型 | 推荐配置 | 月费区间 |
|---------|---------|---------|
| 个人博客（日访 <500） | 1 核 1G + 25Mbps | ¥25-35/月 |
| 中小企业站（日访 500-5000） | 2 核 2G + 30-50Mbps | ¥60-90/月 |
| 内容站/资讯站（日访 5000-2 万） | 4 核 4G + 40Mbps | ¥100-150/月 |
| WooCommerce 商城 | 4 核 8G + 50Mbps | ¥150-180/月 |
| 大流量门户（日访 >2 万） | 独立服务器 | ¥400+/月 |

## 几个常被问到的细节

**经典云流量用完会断网吗？**

不会。流量用完后带宽会降为最低值，但不停机不断网，下个计费月自动清零。这点比很多海外厂商动辄停机的策略厚道。

**弹性云和经典云能互相转吗？**

不能。两者底层架构不同，弹性云是动态资源池，经典云是固定配置包。需要迁移的话，建议新开一台、用迁移插件（如 All-in-One WP Migration）搬站，再销毁旧的。

**香港节点需要备案吗？**

不需要。香港、韩国、日本、美国节点都不强制备案。只有重庆等国内节点需要先完成 ICP 备案才能绑域名访问。

**支持退款吗？**

弹性云预付费余额一月内可原路退回。经典云开通三日内、IP 完好、流量消耗不超过 5% 可发工单销毁。独立服务器开通 24 小时内可退。比那些"售出概不退款"的厂商友好不少。

## 该怎么选：三种典型用户的建议路径

**场景一：第一次建站的学生/个人**

预算 200 元/年以内，想跑个 WordPress 博客练手。直接选 **香港特惠 hk.mini**（¥150/年），1 核 0.75G 跑轻量博客绑缓存插件完全够用。如果觉得内存紧，加 100 块升到 **hk.small**（¥276/年），1GB 内存更从容。

**场景二：小企业官网或自媒体**

日均几百到几千访问，需要稳定不卡顿。推荐 **香港-KC hk.kc.m**（¥60/月，2 核 2G + 30Mbps + 500GB 流量），用优惠码 `丙午` 8 折后 ¥48/月，年付 ¥480。EPYC 7003 处理器性能很强，跑 WordPress + 几个常用插件毫无压力。

**场景三：流量上来后的升级**

日访破万，或者开始上 WooCommerce 卖货。直接迁移到 **弹性云香港-KC**，2 核 4G 起步，按需升配。或者一步到位上 **hk.kc.xl**（4 核 8G + 45Mbps + 1500GB，¥150/月），8 折后 ¥120/月，跑电商站稳稳的。

## 写在最后

搜 "VPS for WordPress" 的人，其实想要的是一个"不踩坑、不超预算、能跑出 WordPress 真实速度"的方案。海外大厂方案多，但中文用户体验差、价格也不便宜；国内大厂便宜但备案麻烦、配置僵化。狗云卡在这个中间地带——香港节点免备案、中文控制台、套餐选择多、价格梯度合理，从年付 150 元的入门机到月付千元的独立服务器都有覆盖。

如果你想真正动手试试，建议从最便宜的特惠套餐起步，跑通整个 WordPress 部署流程，再根据实际负载决定要不要升级。狗云的弹性云支持按小时计费，试错成本很低。所有套餐的购买入口都在上面的对比表里，点击即可跳转到对应套餐的下单页。

搭 WordPress 这事，说到底就是把"内容"和"基础设施"分开——你专注写文章做内容，机器的事交给靠谱的 VPS。希望这份指南能帮你少走点弯路。
