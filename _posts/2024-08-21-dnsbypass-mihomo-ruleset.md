---
title: 搭载 mihomo 内核进行 DNS 分流教程-ruleset 方案
description: 此方案适用于 Clash，搭载 mihomo 内核并使用其特性进行 DNS 分流。包括 ShellCrash 和 Clash Verge 配置方法
date: 2024-08-21 07:52:58 +0800
categories: [DNS 配置, DNS 分流]
tags: [Clash, mihomo, 进阶, DNS, DNS 分流]
---

注：
- 1. 使用 [ShellCrash](https://github.com/juewuy/ShellCrash) 搭配 [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) 并将 AdGuard Home 作为上游时不要使用该方法
- 2. DNS 分流简单来说就是**指定国内域名走国内 DNS 解析，其它域名包括国外域名走 `fake-ip`**

## 一、 导入规则集合文件
`rule-providers` 须添加 `fakeip-filter` 和 `cn`，如下：

```yaml
rule-providers:
  fakeip-filter:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/fakeip-filter.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/fakeip-filter.mrs"
    interval: 86400

  cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/clash-ruleset/cn.mrs"
    interval: 86400
```

## 二、 DNS 分流配置（以 ShellCrash 为例）
1. 进入主菜单 -> 2 内核功能设置 -> 2 切换 DNS 运行模式，选择“3 mix混合模式”  
<img src="/assets/img/dns/dns-mix.png" alt="ShellCrash DNS 运行模式设置" width="60%" />

2. 进入主菜单 -> 2 内核功能设置 -> 2 切换 DNS 运行模式 -> 4 DNS 进阶设置，将“当前基础 DNS”和“PROXY-DNS”都设置为“null”  
<img src="/assets/img/dns/dns-null.png" alt="ShellCrash DNS 进阶设置" width="60%" />

3. 连接 SSH 后执行命令 `vi $CRASHDIR/yamls/user.yaml`，按一下 Ins 键（Insert 键），粘贴如下内容：

```yaml
hosts:
  doh.pub: [1.12.12.12, 120.53.53.53, 2402:4e00::]
  dns.alidns.com: [223.5.5.5, 223.6.6.6, 2400:3200::1, 2400:3200:baba::1]

dns:
  enable: true
  ipv6: true
  listen: 0.0.0.0:1053
  fake-ip-range: 198.18.0.1/16
  enhanced-mode: fake-ip
  fake-ip-filter: ['rule-set:fakeip-filter,cn']
  nameserver:
    - https://doh.pub/dns-query
    - https://dns.alidns.com/dns-query
  direct-nameserver:
    - https://doh.pub/dns-query
    - https://dns.alidns.com/dns-query
```

按一下 Esc 键（退出键），输入英文冒号 `:`，继续输入 `wq` 并回车
