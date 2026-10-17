<div align="center">

# 窑变 for Obsidian

<img src="assets/hero.png" width="880" alt="窑变 · 入窑一色，出窑万彩" />

> 入窑一色，出窑万彩。

**中文** · [English](README.md)

[上游 Composer](https://github.com/vran-dev/obsidian-composer) · [配色来源 窑变](https://github.com/Sum-su/yaobian-theme)

</div>

---

## 简介

一个 Obsidian 主题，fork 自 [Composer](https://github.com/vran-dev/obsidian-composer) 并做了个性化改造，为更舒适的阅读与写作体验设计。主题内置 **39 套配色方案**（深浅双轨），全部通过 `style settings` 插件切换；保留上游的排版基因——段落字距 / 行高、标题装饰与 Callout 样式，表格、列表与高亮则交由 Obsidian 原生。

## 相比上游的改动

- **移除**「霓」配色方案，及 [Components](https://cp.cc1234.cc/) 插件相关的全部设置与样式
- **移除**「色彩设置」整节（背景取色器、彩虹目录微调），配色完全交由配色方案接管
- **移除** 表格、列表与高亮样式（含 `--highlight-opacity`），交由 Obsidian 原生渲染，可另用插件接管
- **新增** 72 套配色（36 族 × 深浅），每族强调色取自其主色，并保证对编辑区背景 ≥ 2.5:1 对比度
- **修正** 上游遗留问题：视图标题路径折叠开关的设置项与样式选择器不一致

## 配色方案

> [!NOTE]
> 切换配色需先安装 [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) 插件，亮色 / 暗色各选一套。

**内置 · 源自上游（3 族）**

- Xiá 霞 · Sù 素 · Qīng 青

**移植 · 源自 yaobian-theme（36 族 × 深浅 = 72 套）**

中国风 · 25 族

- 禅棕 `chan-zong` · 长安 `chang-an` · 春梅 `chun-mei` · 丹霞 `dan-xia` · 汉白玉 `han-bai-yu`
- 湖光 `hu-guang` · 金镶玉 `jin-xiang-yu` · 流云 `liu-yun` · 琵琶 `pi-pa` · 青瓷 `qing-ci`
- 青花 `qing-hua` · 青雾 `qing-wu` · 汝窑蓝 `ru-yao-lan` · 汝窑绿 `ru-yao-lv` · 山水 `shan-shui`
- 素宣 `su-xuan` · 天水 `tian-shui` · 宣纸 `xuan-zhi` · 雁灰 `yan-hui` · 烟雨 `yan-yu`
- 胭脂 `yan-zhi` · 羊皮纸 `yang-pi-zhi` · 窑火 `yao-huo` · 玉石 `yu-shi` · 紫陶 `zi-tao`

其他 · 11 族

- Claude `claude` · Claude·Auroral `claude-auroral` · Dopamine · Dracula · 歌蕾蒂娅 `gladiia`
- Mint · 莫奈 `mo-nai` · 暮山紫 `mu-shan-zi` · 奶茶 `nai-cha`
- Peppa · Pulse · Vitesse Soft

## 快速开始

1. 下载 `theme.css`，放入库目录 `.obsidian/themes/Yaobian/` 下
2. 设置 → 外观 → 主题，选择 **Yaobian**
3. 安装 [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) 插件，在主题设置中切换配色方案

> [!TIP]
> 想让每套配色展示各自的强调色，请将 Obsidian「外观 → 强调色」保持为默认——手动设置过的强调色会覆盖主题值。

## 开发说明

**移植逻辑** —— 36 族配色取自 [yaobian-theme](https://github.com/Sum-su/yaobian-theme) 的 72 份 VS Code 主题定义：`editor.background` / `editor.foreground` 生成背景与十二档色阶，`button.background` 作为各族强调色（换算 HSL，微调明度以保证对背景 ≥ 2.5:1），`sideBar`、`textBlockquote`、`textCodeBlock` 等键分别映射到 Obsidian 的对应变量；文字高亮跟随 Obsidian 原生（对齐上游 PR #58）。

**构建逻辑** —— 样式设置与样式主体分离维护：`settings.yml` 声明 Style Settings 选项，`yaobian.css` 存放全部样式，由 `build.mjs` 合并生成最终的 `theme.css`。

```bash
npm run build        # settings.yml + yaobian.css -> theme.css
npm version patch    # 发版：自动构建并同步 manifest.json / versions.json
```

> [!NOTE]
> `theme.css` 为构建产物，请勿手改其中的 YAML 头部。

## 鸣谢

- 本主题 fork 自 @vran 的 [Composer 主题](https://github.com/vran-dev/obsidian-composer)
- 配色移植自 @Sum-su 的 [yaobian-theme](https://github.com/Sum-su/yaobian-theme)（窑变），其颜色源自 [cherrycss.com](https://cherrycss.com) 主题画廊
- Claude·Auroral 配色移植自 @AuroralFrost 的 [claude-light-theme](https://github.com/AuroralFrost/claude-light-theme)（深浅成对的 VS Code 主题），与原版 Claude 并存

---

<div align="center">

以 MIT 许可发布 · 窑变，釉色万千

</div>
