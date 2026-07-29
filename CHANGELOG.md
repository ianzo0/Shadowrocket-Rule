# Changelog

## 0.1.2 — 2026-07-30

- 将“节点选择”、AI、Google 与 Meta 的默认出口统一为通用自动测速；美国、日本、新加坡、香港等地区组改为可选的手动出口。
- 写入正式 GitHub 更新地址，导入 Shadowrocket 后可直接检查并更新配置。

## 0.1.1 — 2026-07-30

- 修复三套配置中 TikTok 远程规则地址被策略组图标误改的问题。
- 更新 GitHub Actions 校验目标，改为检查 `ianzo-rule-cn.conf`、`ianzo-rule-full.conf` 和 `ianzo-rule-gfw.conf`。
- 为局域网、公共 Wi-Fi 认证、微信本地回调和 Apple 推送加入 `always-real-ip` 排除项。
- 收紧 Google 中国入口重写的主机名边界。
- 补充全量版规则规模、Fake-IP 边界、地区节点命名要求和 GFW 版未使用策略组说明。

## 0.1.0 — 2026-07-29

- 创建独立项目骨架。
- 添加具备逐行中文说明的 `ianzo-rule-cn.conf` 最小可测试配置。
- 加入局域网、AI 与开发、国际媒体、即时通讯、Apple 服务和中国大陆 IP 的基础分流。
- 增加加密 DNS 回退、常见硬编码 DNS 劫持、Google、TikTok 与 Meta 的最小可审查规则。
- 重写地区节点分组，支持香港、美国、日本、台湾、新加坡和其他节点的自动测速与服务级切换。
- 增加独立的 Apple Push Notification service 分流策略与 `push.apple.com` 规则。
- 拆分 Telegram 与 X（原 Twitter）策略组，使两类服务可独立选择出口。
- 增加 Apple、Android 与 Windows 的公共 Wi-Fi 认证/连通性探测直连规则，以及微信显式直连规则。
- 增加 g.cn、google.cn 到 www.google.com 的 URL Rewrite，并将 MITM 范围限制为这些域名。
- 新增全量规则版与 GFW 模式；新增第三方远程规则来源登记文档。
- 将服务分流拆为 AI 与代码托管两组，并改为引用第三方 Shadowrocket 专用规则集。
- 将“国际流媒体”更名为“流媒体 Netflix/Disney+”，并加入默认直连、可手动切换香港节点的券商服务规则。
- 添加项目说明、许可证和审计文档占位。
