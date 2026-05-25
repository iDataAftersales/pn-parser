# PN解析工具 - iData BOM命名规范

🔗 **在线使用：** [https://你的用户名.github.io/pn-parser/](https://你的用户名.github.io/pn-parser/)

## 功能介绍

基于 iData BOM 命名规范表格，自动解析 PN（Part Number）码的每个字段含义。

### 支持的产品系列（共239个）

- A50P, 95WP-2, T3-2, K3S-1, T3-PRO, P9mini 等
- 覆盖 iData 全系列产品

### 解析示例

| PN码 | 产品系列 | 配置码 |
|------|----------|---------|
| `A50P-FMA182240-2200` | iData 50P（A50P）（停产） | FMA182240 |
| `95WP-2-S0E86101-1100` | 95W Pro(95WP-2 MT8786) | S0E86101 |
| `T3-2-WMC96C220-1FAXZ` | T3-2(SF01) | WMC96C220 |

## 本地使用

无需服务器，双击 `index.html` 即可在浏览器中使用。

## 数据源

- **命名规范表**：`iData BOM命名规范_V6.03_20260509.xlsx`
- **产品系列数**：239个
- **更新日期**：2026-05-25

## 技术实现

- 纯前端实现（HTML + JavaScript）
- 内置所有产品系列配置数据（约600KB）
- 无需后端服务器
- 无需网络连接（离线可用）

## 部署到 GitHub Pages

1. Fork 或 Clone 本仓库
2. 在仓库设置中开启 GitHub Pages
3. 选择 `main` 分支，`/ (root)` 目录
4. 访问 `https://你的用户名.github.io/pn-parser/`

## 部署到 Vercel

1. 访问 [vercel.com](https://vercel.com)
2. 点击 "Add New..." → "Project"
3. 拖拽 `index.html` 到页面
4. 自动部署，获得网址

## 集成到 Dify

HTTP API 调用示例（待部署后提供）：

```bash
curl -X POST https://你的网址.vercel.app/api/parse \
  -H "Content-Type: application/json" \
  -d '{"pn": "A50P-FMA182240-2200"}'
```

## 更新配置

当命名规范表更新时：

```bash
python extract_all_configs.py  # 重新提取配置
python generate_html.py         # 重新生成 index.html
```

## 授权

内部工具，仅供 iData 员工使用。
