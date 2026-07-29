# 第三方规则来源

本项目所有配置均以远程引用方式使用第三方规则集；规则内容不会复制或提交到本仓库。

## blackmatrix7/ios_rule_script

- 项目：<https://github.com/blackmatrix7/ios_rule_script>
- 使用格式：仅引用 `rule/Shadowrocket/` 下各服务的专用 `.list` 文件。
- 使用范围：OpenAI、Anthropic、Claude、GitHub、GitLab、Atlassian、YouTube、Netflix、Disney、Spotify、Google、TikTok、Facebook、Telegram、Twitter、Apple。
- 使用方式：三份配置均通过 `RULE-SET` 远程引用；不复制或再发布该项目的规则内容。
- 责任边界：上游项目有自己的免责声明和转载限制；本项目仅登记远程依赖，规则内容、许可证和维护状态以其上游仓库声明为准。

## Loyalsoldier/surge-rules

- 项目：<https://github.com/Loyalsoldier/surge-rules>
- 使用分支：`release`
- 使用格式：`ruleset/*.txt`，以 Shadowrocket 的 `RULE-SET` 远程引用。
- 全量规则版：`private.txt`、`reject.txt`、`direct.txt`、`proxy.txt`。
- GFW 模式：`gfw.txt`。
- 更新策略：上游项目通过 GitHub Actions 定期构建；本项目不复制其规则内容。
- 责任边界：规则的准确性、可用性、更新和许可证以其上游仓库声明为准。

## LingJingMaster/Shadowrocket-Rules

- 项目：<https://github.com/LingJingMaster/Shadowrocket-Rules>
- 使用文件：`AI.list`、`HK_Broker.list`。
- 使用范围：`AI.list` 作为 OpenAI、Anthropic、Claude 专用规则之外的 AI 服务补充，例如 xAI、Grok 等；`HK_Broker.list` 为香港券商相关域名提供独立分流。
- 使用方式：三份配置均通过 `RULE-SET` 远程引用；香港券商规则默认使用香港节点，用户应按券商要求选择并长期使用稳定的单一节点；不复制或再发布这些文件内容。
- 责任边界：规则内容、许可证和维护状态以其上游仓库声明为准。

## 使用原则

1. 每次新增外部规则前，记录项目、文件、用途、格式和启用日期。
2. 只引用明确适配 Surge/Shadowrocket 语法的规则文件。
3. 第三方规则失效或误分流时，优先禁用对应引用，不把上游文件复制入仓库修补。
4. 全量和 GFW 模式属于可选配置；用户应在 Shadowrocket 中先测试网络、DNS 与流媒体可用性。
