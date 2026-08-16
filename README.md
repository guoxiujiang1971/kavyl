# Kavyl（凯薇）

> 会记住你、不会突然变心的治愈系 AI 陪伴 —— 情绪健康型 AI 陪伴 + 情绪记录 iOS App。

Kavyl 是面向 18-30 岁年轻人群的「情绪健康型」AI 陪伴应用：像懂你的朋友，而不是恋人。核心能力是 **真记忆**（主动回访、用户可管理）、**人格稳定协议**（更新不变人设）、**克制而安全的对话**，加上情绪打卡、呼吸练习、晚安信等轻治愈功能。

- 目标市场：欧美为主，App Store 分级 17+
- 隐私最强路线：LLM 用 Apple Foundation Models（端上 + Private Cloud Compute），不挂任何第三方 LLM Key
- 后端：Supabase（Postgres + pgvector + Auth + Edge Functions + Realtime）

---

## 技术栈

| 层 | 方案 |
|---|---|
| iOS 客户端 | SwiftUI + Swift Concurrency，iOS 17+（含 Widget / Watch / 灵动岛） |
| 项目生成 | [XcodeGen](https://github.com/yonaskolb/XcodeGen)（`ios/project.yml`） |
| AI 对话 | Apple Foundation Models（端上优先 + PCC），零计费 |
| 语音 | 系统 Speech / Sensory（全端上） |
| 后端 | Supabase：Postgres + pgvector + Auth + Edge Functions + Realtime |
| 推送 | Supabase Cron + Edge Function 调 APNs |
| 依赖 | supabase-swift 2.54+ |

---

## 目录结构

```
├── ios/                      # iOS 工程（XcodeGen 生成 .xcodeproj）
│   ├── project.yml           # XcodeGen 配置
│   ├── Kavyl/                # 主 App（SwiftUI）
│   │   ├── AppConfig.swift   # Supabase URL / anon key / bundle id
│   │   ├── Services/         # 对话、记忆、情绪、订阅等服务
│   │   ├── Models/           # 数据模型
│   │   ├── Views/            # 界面
│   │   └── Resources/        # Info.plist / entitlements / 资源
│   ├── KavylWidget/          # 桌面小组件
│   ├── KavylWatch/           # Apple Watch App
│   └── Shared/               # App / Widget / Watch 共享代码
├── supabase/                 # 后端
│   ├── config.toml           # Supabase CLI 配置
│   ├── migrations/           # 数据库迁移（含 RLS、订阅、危机干预等）
│   ├── seed/  seed.sql       # 种子数据（角色、预设头像等）
│   └── functions/            # Edge Functions
│       ├── chat-proxy/       # 对话代理
│       ├── purchase-verify/  # IAP 验签
│       ├── apns-push/        # APNs 推送
│       ├── memory-maintenance/ # 记忆维护（清理/合并）
│       ├── greeting-card/    # 晚安信/问候卡片
│       └── set-character-avatar/ # 角色头像
├── avatars_upload/           # 本地生成的头像素材（不入库）
├── icon/                     # App 图标源文件
├── keys/                     # 私钥（.p8 等，切勿提交，已被 .gitignore 忽略）
└── docs/                     # 产品 / 后端 / 合规 / 隐私政策文档
```

---

## 环境要求

- macOS + Xcode 16+
- [XcodeGen](https://github.com/yonaskolb/XcodeGen)（`brew install xcodegen`）
- [Supabase CLI](https://supabase.com/docs/guides/cli)（本地开发 / 迁移用）
- iPhone 15 Pro+ / M 系设备可获得最佳端上模型体验（老设备降级走 Private Cloud Compute）

---

## 快速开始

### 1. 克隆并生成 iOS 工程

```bash
git clone <repo-url> Kavyl
cd Kavyl/ios
xcodegen generate
open Kavyl.xcodeproj
```

> `.xcodeproj` 由 XcodeGen 生成，已加入 `.gitignore`，不要手工修改。

### 2. 配置后端

```bash
cd supabase
supabase login
supabase link --project-ref <your-project-ref>
supabase db push        # 应用 migrations
supabase db seed --local # 或对远端执行 seed.sql
```

Edge Functions 部署：

```bash
supabase functions deploy chat-proxy
supabase functions deploy purchase-verify
supabase functions deploy apns-push
supabase functions deploy memory-maintenance
supabase functions deploy greeting-card
supabase functions deploy set-character-avatar
```

各函数所需环境变量见 `supabase/functions/<fn>/index.ts` 顶部注释（APNs key、IAP 验签 key 等）。

### 3. 配置 iOS 端

- 将 `ios/Kavyl/AppConfig.swift` 中的 `supabaseURL` / `supabaseAnonKey` 指向你的 Supabase 项目。
- 在 Xcode 中配置自己的 `DEVELOPMENT_TEAM` 与签名（`ios/project.yml` 中当前为自动签名的占位值）。

### 4. 运行

选择 `Kavyl` scheme（配好签名与设备/模拟器）直接 Run。

---

## 密钥与安全

- `keys/`、`*.p8`、`supabase/.env`、`.env` 等均已加入 `.gitignore`，**严禁提交任何私钥、APNs key、IAP 密钥或 Supabase service key**。
- `AppConfig.swift` 中的 Supabase anon key 为公开客户端 key，仅用于匿名访问；后端权限依赖 RLS 与 Edge Function 校验，不要依赖客户端 key 做安全边界。

---

## 文档

| 文档 | 说明 |
|---|---|
| `docs/MVP-产品方案.md` | 产品定位、差异化策略、MVP 功能范围、体验设计 |
| `docs/MVP-后端设计.md` | 架构、数据模型、对话/记忆/订阅流程、成本 |
| `docs/合规材料清单.md` | App Store 上架合规清单（隐私政策、COPPA、订阅话术等） |
| `docs/privacy-policy-en.md` | 英文隐私政策（发布前替换联系邮箱并挂公开 URL） |
| `docs/app-store-screenshots.md` | App Store 截图规范 |
| `docs/功能规划.md` / `docs/编程指示.md` | 功能规划与开发约定 |

---

## 合规要点（上架前必读）

- 年龄分级 **17+**，明确不面向 13 岁以下（COPPA），后端对 `0-12` 年龄带拒绝建号。
- 提供数据导出 / 账号删除（GDPR），记忆内容用户可查看、编辑、删除。
- AI 身份透明（明示「AI 非真人」）+ 危机干预（多国热线映射）。
- 订阅走 Apple IAP，不得引导外部支付。

详见 `docs/合规材料清单.md`。

---

## License

内部项目，暂未开源。
