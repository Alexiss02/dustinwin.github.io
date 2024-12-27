# 关于
1. [本教程合集](https://proxy-tutorials.dustinwin.top)基于 [mihomo 内核](https://github.com/MetaCubeX/mihomo)和 [sing-box PuerNya 版内核](https://github.com/PuerNya/sing-box/tree/building)编写，请尽量使用最新版内核，可到 [DustinWin/proxy-tools](https://github.com/DustinWin/proxy-tools) 项目进行更新
2. 本教程合集分为五大类，分别为：[置顶](https://proxy-tutorials.dustinwin.top/categories/%E7%BD%AE%E9%A1%B6/)、[直链配置](https://proxy-tutorials.dustinwin.top/categories/%E7%9B%B4%E9%93%BE%E9%85%8D%E7%BD%AE/)、[工具配置](https://proxy-tutorials.dustinwin.top/categories/%E5%B7%A5%E5%85%B7%E9%85%8D%E7%BD%AE/)、[DNS 配置](https://proxy-tutorials.dustinwin.top/categories/dns-%E9%85%8D%E7%BD%AE/)和[分享配置](https://proxy-tutorials.dustinwin.top/categories/%E5%88%86%E4%BA%AB%E9%85%8D%E7%BD%AE/)。伸手党可直接进入分享配置进行参考，请尽量使用我定制的[规则集文件](https://github.com/DustinWin/ruleset_geodata)
3. 本教程合集偏向于实操，基础配置的搭载内核和 Wiki 文档对应关系如下表：

|   搭载内核    |         mihomo 内核          |       sing-box PuerNya 版内核        |           sing-box 内核            |
| :-----------: | :--------------------------: | :----------------------------------: | :--------------------------------: |
| **Wiki 文档** | <https://wiki.metacubex.one> | <https://sing-boxp.dustinwin.top/zh> | <https://sing-box.sagernet.org/zh> |

# 对 geodata 和 ruleset 方案的说明
1. geodata 方案更适用于路由器等设备（连接多台设备而无法判断非本机设备进程），配置文件编写简单，对小白用户友好
2. ruleset 方案适用于对分流规则要求比较严格的用户，配置文件编写复杂，可按需配置且配置灵活
3. mihomo 采用 geodata 方案，使用 `GEOSITE` 和 `GEOIP` 规则搭配 GeoSite.dat 和 GeoIP.dat（或 Country.mmdb）[路由规则文件](https://github.com/DustinWin/ruleset_geodata?tab=readme-ov-file#%E4%B8%80-geodata-%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E)
4. mihomo 采用 ruleset 方案，采用 `RULE-SET` 规则搭配 .yaml、.text 和 .mrs [规则集文件](https://github.com/DustinWin/ruleset_geodata?tab=readme-ov-file#%E4%BA%8C-ruleset-%E8%A7%84%E5%88%99%E9%9B%86%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E)
5. sing-box 采用 geodata 方案，使用 `GEOSITE` 和 `GEOIP` 规则搭配 geosite.db 和 geoip.db [路由规则文件](https://github.com/DustinWin/ruleset_geodata?tab=readme-ov-file#%E4%B8%80-geodata-%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E)
6. sing-box 采用 ruleset 方案，采用 `rule_set` 规则搭配 .srs 和 .json [规则集文件](https://github.com/DustinWin/ruleset_geodata?tab=readme-ov-file#%E4%BA%8C-ruleset-%E8%A7%84%E5%88%99%E9%9B%86%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E)

# 对下载源的说明
1. 本教程默认下载源为 [jsDelivr 源](https://www.jsdelivr.com/github)，地址前缀为 `https://cdn.jsdelivr.net/gh/xxx`，此源中**文件更新有 12 小时延迟**
2. 若 jsDelivr 源无法访问，可将地址前缀改为 `https://fastly.jsdelivr.net/gh/xxx`
3. 推荐使用 [GitHub 源](https://github.com)，地址前缀分别为 `https://github.com/xxx` 和 `https://raw.githubusercontent.com/xxx`
4. 若 GitHub 源无法访问，可在链接上添加 `https://ghgo.xyz/` 前缀，即：将地址分别改为 `https://ghgo.xyz/https://github.com/xxx` 和 `https://ghgo.xyz/https://raw.githubusercontent.com/xxx`
5. jsDelivr 源和 GitHub 源格式如下：  
- ① jsDelivr 源格式为 `https://cdn.jsdelivr.net/gh/[username]/[reponame]@[branchname]/[filename]`  
- ② GitHub 源格式为 `https://github.com/[username]/[reponame]/releases/download/[branchname]/[filename]`（推荐）和 `https://raw.githubusercontent.com/[username]/[reponame]/[branchname]/[filename]`

# 给作者加鸡腿
支付宝  
<img src="/assets/img/about/alipay.jpg" alt="支付宝" width="20%" />

# 机场推荐
[Bitz Net](https://rd2.bnaffloop.com/#/register?code=HT0ALWZq)（仅次于一线机场，推荐打折时购买）  
85 折优惠码：`TURKEY24`（有效期至 2024 年 12 月 1 日 23:59 分）
