# 全国热力图

上传一张 Excel，全国地图上按数值深浅给 31 个省级机构上色。支持自定义配色（渐变或按区间取色）、数值 / 百分比两种口径、导出 PNG。

**页面本身不带任何数据**，机构名单只是 31 个省级标签，数字全部由你自己导入。

[打开工具 →](https://abububu903.github.io/china-heatmap/) · [English](#english)

---

## 打开就用

👉 **[abububu903.github.io/china-heatmap](https://abububu903.github.io/china-heatmap/)**

不用安装、不用注册。想本地跑：下载 `index.html` 双击打开即可。

> 需要联网的只有两个库：ECharts（画图）和 SheetJS（解析 Excel），都从 CDN 加载。你的 Excel 在浏览器本地解析，**不会上传到任何服务器**。

## 三步跑通

1. 点「模板下载」拿到 Excel 模板
2. 按模板填两列：**机构**（必须是下面 31 个名字之一）、**数据**
3. 把文件拖到上传区（或点「快速导入」）→ 先看「数据预览」→ 点「确认导入」，地图立刻上色

## 一个例子

填 `广东 120`、`江苏 95`、`四川 40`，数据类型选「数值」，热力范围点「自动」→
广东最深、四川最浅，其余省份显示为中性灰（表示无数据，不是 0）。
把「数据类型」切成「百分比 (%)」，同一份数字改按 % 显示。

## ⚠️ 只认省级名称，不认城市

市级机构已不再支持。Excel 里写 `深圳`、`东莞`、`苏州` 这类城市名**匹配不上**，
对应的值不会出现在地图上，也不报错。要按城市看，请自己先把城市数据汇总到所属省再导入。

## 功能清单

| 功能 | 说明 |
| --- | --- |
| 快速导入 | 拖拽或点击上传 Excel，导入前有「数据预览」确认 |
| 模板下载 | 给出标准两列模板，避免列名对不上 |
| 机构数据 | 侧栏手工增改单个机构数值，适合只改几格 |
| 渐变配色 | 最小 / 中间 / 最大三色线性渐变，可调热力范围 |
| 区间值配色 | 自定义区间各配一色，支持增删、「按数据均分」算边界、保存配色方案 |
| 数据类型 | 百分比 (%) / 数值 两种口径切换 |
| 字体设置 | 数值颜色与字号、机构名称颜色与字号 |
| 下载 PNG | 当前地图导出图片，直接贴 PPT |
| 数据微调 | 导入前修正机构名与数值 |

### 区间配色的一条规则

区间含上下限，边界值归入靠前的区间；未落入任何区间的值显示为浅灰。「按数据均分」按当前区间条数，用数据的最小 / 最大值等分边界。

## 31 个机构名单

北京、天津、上海、重庆、河北、山西、内蒙古、辽宁、吉林、黑龙江、江苏、浙江、安徽、福建、江西、山东、河南、湖北、湖南、广东、广西、海南、四川、贵州、云南、西藏、陕西、甘肃、青海、宁夏、新疆

名单外的名称一律匹配不上，导入时看「数据预览」确认。

## 免责

作者：abububu903

- 结果完全取决于你导入的数据，工具不做任何统计加工或校验
- 地图轮廓为简化示意数据，**南海诸岛及九段线未绘制**，港澳台仅作为无数据区域显示；正式场合请使用自然资源部标准地图
- 配色、字体等设置在刷新后不保留（区间配色方案可保存）

## 文件说明

| 文件 | 作用 |
| --- | --- |
| `index.html` | 工具本体，页面 + 逻辑 + 内嵌地图轮廓与模板（约 640 KB） |
| `README.md` | 你正在看的这个说明页，GitHub 自动展示在仓库首页 |

---

## English

A single-file heatmap template for China: drop in a two-column spreadsheet (institution name + value) and the map shades each of the 31 provincial-level regions by that value. Export as PNG for slides.

- **Live page:** <https://abububu903.github.io/china-heatmap/> — no install, no sign-up. Or download `index.html` and open it directly.
- **No data is bundled.** The 31 institutions are just province-level labels with coordinates; every number comes from your own file.
- **Privacy:** the spreadsheet is parsed in your browser via SheetJS and never uploaded. Only the ECharts and SheetJS libraries load from a CDN.
- **Province-level only.** City names such as Shenzhen or Suzhou no longer match — values for them are silently dropped. Aggregate to the province first.
- **Two colouring modes:** a min/mid/max gradient, or custom value ranges with one colour each, including "split evenly by data range" and saved presets.
- **Limits:** the basemap is a simplified outline — the South China Sea islands and nine-dash line are not drawn, and Hong Kong / Macau / Taiwan render only as no-data areas. Use the official standard map for anything formal. Settings do not persist across reloads.

*By abububu903.*
