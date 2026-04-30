# Home Assistant 统一账单卡片

![Version](https://img.shields.io/badge/version-v1.0.0-blue)
![HA Version](https://img.shields.io/badge/Home%20Assistant-2024.1%2B-green)
![License](https://img.shields.io/badge/license-MIT-orange)

支持温州水务和华润燃气的 Home Assistant Lovelace 仪表盘卡片。

## 支持的集成

| 集成 | 实体前缀 | 图标 |
|------|----------|------|
| [温州水务](https://github.com/C3H3-AI/ha-wenzhou-water) | `wenzhou_water` | 💧 |
| [华润燃气](https://github.com/C3H3-AI/ha-crcgas) | `crcgas` | 🔥 |

## 功能

- 💰 账户余额显示
- 📊 本期用量统计
- 🔢 当前阶梯指示
- 💵 预估账单金额
- 📈 阶梯用量进度条
- 📉 与历史均值对比
- ⚡ 实时状态指示灯

## 安装

### 通过 HACS 安装（推荐）

1. 打开 [HACS](https://hacs.xyz/)
2. 点击 **仪表盘** (Dashboard)
3. 点击右上角 `+` 添加
4. 搜索 **Utility Bill Card** 或 **统一账单卡片**
5. 点击安装

安装后卡片会自动注册，**无需手动添加资源引用**！

### 手动安装

1. 下载 `dist/ha-utility-bill-card.js`
2. 复制到 `config/www/community/utility-bill-card/`
3. 在 Home Assistant 中添加资源引用：
   - 设置 → 仪表盘 → 资源
   - 添加资源：`/local/community/utility-bill-card/ha-utility-bill-card.js`
   - 类型：JavaScript 模块

## 使用

### 添加卡片

```yaml
type: custom:ha-utility-bill-card
entity: sensor.wenzhou_water_账户余额
title: 温州水务
```

或：

```yaml
type: custom:ha-utility-bill-card
entity: sensor.crcgas_account_balance
title: 华润燃气
```

### 配置参数

| 参数 | 说明 | 默认值 |
|------|------|--------|
| `entity` | 账单实体（任意一个即可） | **必填** |
| `title` | 卡片标题 | `公用事业` |

## 示例

### 温州水务

```yaml
type: custom:ha-utility-bill-card
entity: sensor.wenzhou_water_账户余额
title: 温州水务
```

### 华润燃气

```yaml
type: custom:ha-utility-bill-card
entity: sensor.crcgas_account_balance
title: 华润燃气
```

## 预览

卡片会自动识别实体类型并显示对应的图标和标签：

- 💧 水务模式：显示"本期用水"、"月均用水"等
- 🔥 燃气模式：显示"本期用气"、"月均用气"等

## 问题反馈

https://github.com/C3H3-AI/ha-utility-bill-card/issues
