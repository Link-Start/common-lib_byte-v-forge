# common-lib

`common-lib` 是 byte-v-forge 的跨仓公共能力仓，沉淀稳定契约、基础设施 helper 和共享前端基础组件。

## 核心能力

- 提供跨服务公开 proto 契约与 Go/TypeScript 生成物，作为平台公共模型和 gRPC service 的真源。
- 提供无业务语义的通用库：HTTP/gRPC client、Redis、事件总线、outbox、分页、时间、随机、脱敏、JSON、proto JSON 等基础能力。
- 提供共享 React/shadcn dashboard uikit 与通用数据驱动组件，支撑业务模块轻量装配页面。
- 提供契约边界、事件 catalog 和破坏性变更检查脚本，辅助多仓协同演进。

## 边界

本仓只放跨仓稳定能力，不承载 GPT、Mailbox、SMS、Proxy、Browser Automation 等业务流程、provider 分支、页面或私有状态机。业务仓通过发布包、proto/gRPC、HTTP 或事件边界消费公共能力。

## 入口

- 公共契约：`proto/byte/v/forge/contracts/`
- Go 生成物：`gen/go/byte/v/forge/contracts/`
- 共享前端包：`ui/`
- 分层说明：`docs/layers.md`

## 常用检查

```sh
sh scripts/generate-proto.sh
sh scripts/generate-web-proto.sh
sh scripts/check-boundaries.sh
git diff --check
```
