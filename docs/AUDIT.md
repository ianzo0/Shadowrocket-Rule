# 配置审计记录

## 0.1.1

状态：静态修复完成，待 iPhone 实机验证和 GitHub 发布。

发布前需要检查：

- Shadowrocket 配置语法和策略组引用；
- DNS 解析与回退行为；
- 节点名称地区匹配；
- 规则顺序和冲突；
- 所有第三方远程规则的可用性、来源和许可证；
- 是否包含订阅地址、账号、密钥、证书或个人网络信息；
- GitHub Raw 更新地址；
- iPhone 实机导入、连接、更新和回滚。

## 三套配置的额外检查

- `ianzo-rule-cn.conf`：基础平衡版，引用 blackmatrix7 的 Shadowrocket 服务专用规则集。
- `ianzo-rule-full.conf`：引用 `private`、`reject`、`direct`、`proxy` 四个 Loyalsoldier 远程规则集；2026-07-30 链接检测均返回 HTTP 200。
- `ianzo-rule-gfw.conf`：在服务分流后引用 Loyalsoldier `gfw` 远程规则集，随后 `FINAL,DIRECT`；2026-07-30 链接检测返回 HTTP 200。
- 三份配置引用的 16 个 blackmatrix7 Shadowrocket 服务规则链接与 5 个 Loyalsoldier 规则链接已于 2026-07-30 检查，均返回 HTTP 200。
- 三份配置引用的 LingJingMaster `AI.list` 与 `HK_Broker.list` 链接已于 2026-07-30 检查，返回 HTTP 200。
- 三份配置的 TikTok 规则地址已修复为 blackmatrix7 官方 Shadowrocket 路径，并重新检查返回 HTTP 200。
- 三份配置新增 `always-real-ip` 排除项，用于局域网、公共 Wi-Fi 认证、微信本地回调和 Apple 推送；需实机验证 Fake-IP/TUN 行为。
- 全量版四个 Loyalsoldier 规则集约含 309,193 条上游规则，检测到 direct/reject/proxy 之间存在重复项；按配置顺序由 reject、direct、proxy 依次优先处理。
- GFW 版保留“国内网络”和“未命中的境外流量”策略组供手动选择，但最终规则为 `FINAL,DIRECT`，这两个组不参与自动兜底。
- HTTP 200 仅表示规则可下载，发布前仍必须在 Shadowrocket 实机检查导入、规则编译、DNS、流媒体、Apple 推送和回滚行为。
