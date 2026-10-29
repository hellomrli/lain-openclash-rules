# Lain OpenClash Rules

Lain 标准版规则：为 OpenClash / Mihomo 订阅转换准备的精简规则模板。

## 特点

- 不包含机场订阅链接
- 不包含节点名称、节点地址或节点信息
- 仅保留香港 / 美国 / 日本三个地区节点组
- 移除 YouTube、Netflix、Disney+、HBO、PrimeVideo 等媒体细分策略组；保留 Steam 与 Bahamut
- 增加 AI 服务、日本服务、乌龟服、Bilibili 策略组，并保留 Steam、Bahamut 独立组

## 远程配置地址

```text
https://raw.githubusercontent.com/hellomrli/lain-openclash-rules/main/cfg/Lain_Standard.ini
```

jsDelivr：

```text
https://testingcf.jsdelivr.net/gh/hellomrli/lain-openclash-rules@main/cfg/Lain_Standard.ini
```

## 来源与署名

本模板基于 Aethersailor/Custom_OpenClash_Rules 的思路和部分规则引用进行精简调整。原项目：

https://github.com/Aethersailor/Custom_OpenClash_Rules

当前上游规则镜像：

```text
https://api.asailor.org/Custom_OpenClash_Rules/main/
```

## 备注

- 乌龟服规则包含 `178.249.208.186/32`，模板开启 `udp=true`，用于 TCP/UDP 同时代理。

### 2026-10-29
- **新增**: `🇯🇵 日本服务` 策略组，整合 DMM 与 Abema / Niconico / Pixiv / DLsite / Radiko / TVer，并覆盖 `.jp` 后缀域名。
- **移除**: 独立 `🇯🇵 DMM` 策略组，DMM 规则改指向 `🇯🇵 日本服务`。
- **同步**: 删除 `[]GEOSITE,google-cn` 直连规则（上游于 2026-10-18 从全部模板移除，避免命中后直连失败无法回落）。
- **同步**: `Steam_CDN_Classical.yaml` 更换为 `Game_Download_CDN_Domain.yaml` + `Game_Download_CDN_Classical_IP.yaml`（上游 2026-07-23 将 Steam CDN 合并进游戏下载规则，现覆盖 494 条域名与 23 条 IP 规则）。
- **同步**: 健康检查 URL 由 `https://cp.cloudflare.com/generate_204` 更换为 `https://www.gstatic.com/generate_204`（上游 2026-09-15 统一；gstatic 稳定返回 204，避免强制门户端点返回 200 或重定向造成节点误判）。

## 更新日志

### 2026-07-05
- **同步**: Aethersailor 上游补充规则地址切换为 `api.asailor.org`，修复旧 jsDelivr 地址 404。
- **同步**: 更新香港 / 美国 / 日本节点匹配正则，提升复杂节点名的地区识别率。
- **保留**: 继续维持精简策略组，不恢复 YouTube、Netflix、Disney+、HBO、PrimeVideo 等媒体细分分组。

### 2026-06-10
- **移除**: 删除燕云十六声（YYSLS）全部规则文件及配置引用
