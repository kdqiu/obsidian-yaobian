中文 | [English](README.md)

<div align="center">

# 窑变 for Obsidian

> 一窑烧出万色 —— 同一套釉料，不同火候，各成釉色。

[上游 Composer](https://github.com/vran-dev/obsidian-composer) · [配色来源 窑变](https://github.com/Sum-su/yaobian-theme) · [English](README.md)

</div>

---

## 简介

一个 Obsidian 主题，fork 自 [Composer](https://github.com/vran-dev/obsidian-composer) 并做了个性化改造，为更舒适的阅读与写作体验设计。主题内置 **39 套配色方案**（深浅双轨），全部通过 `style settings` 插件切换。

## 特性

- **39 套配色，深浅成对** —— 保留上游素 / 霞 / 青三族，另移植 [yaobian-theme](https://github.com/Sum-su/yaobian-theme) 全部 36 个配色家族
- **每族专属主题色** —— 强调色取自各家族的主色，并对编辑区背景保证 ≥ 2.5:1 对比度
- **克制的设置面板** —— 移除霓方案、Components 插件与冗余色彩设置，只留排版级选项
- **原版排版基因** —— 段落字距 / 行高、标题装饰、列表符号、Callout 与表格样式悉数保留

## 快速开始

1. 下载 `theme.css`，放入库目录 `.obsidian/themes/Yaobian/` 下
2. 设置 → 外观 → 主题，选择 **Yaobian**
3. 安装 [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) 插件，在主题设置中切换配色方案

> [!TIP]
> 想让每套配色展示各自的强调色，请将 Obsidian「外观 → 强调色」保持为默认——手动设置过的强调色会覆盖主题值。

## 配色方案

**内置 · 源自上游**

| | | |
| --- | --- | --- |
| Xiá 霞 | Sù 素 | Qīng 青 |

**移植 · 源自 yaobian-theme（36 族，各含深浅）**

中国风 · 25 族

| | | | | |
| --- | --- | --- | --- | --- |
| 禅棕 `chan-zong` | 长安 `chang-an` | 春梅 `chun-mei` | 丹霞 `dan-xia` | 汉白玉 `han-bai-yu` |
| 湖光 `hu-guang` | 金镶玉 `jin-xiang-yu` | 流云 `liu-yun` | 琵琶 `pi-pa` | 青瓷 `qing-ci` |
| 青花 `qing-hua` | 青雾 `qing-wu` | 汝窑蓝 `ru-yao-lan` | 汝窑绿 `ru-yao-lv` | 山水 `shan-shui` |
| 素宣 `su-xuan` | 天水 `tian-shui` | 宣纸 `xuan-zhi` | 雁灰 `yan-hui` | 烟雨 `yan-yu` |
| 胭脂 `yan-zhi` | 羊皮纸 `yang-pi-zhi` | 窑火 `yao-huo` | 玉石 `yu-shi` | 紫陶 `zi-tao` |

其他 · 11 族

| | | | | |
| --- | --- | --- | --- | --- |
| Claude | Dopamine | Dracula | 歌蕾蒂娅 `gladiia` | Mint |
| 莫奈 `mo-nai` | 暮山紫 `mu-shan-zi` | 奶茶 `nai-cha` | Peppa | Pulse `pulse-interactive` |
| Vitesse Soft `vitesse-soft` | | | | |

## 相比上游的改动

- **移除**「霓」配色方案，及 [Components](https://cp.cc1234.cc/) 插件相关的全部设置与样式
- **移除**「色彩设置」整节（背景取色器与彩虹目录微调），配色完全交由配色方案接管
- **新增** 72 套配色，并为每套保证强调色对比度
- **修正** 上游遗留问题：视图标题路径折叠开关的设置项与样式选择器不一致

## 鸣谢

- 本主题 fork 自 @vran 的 [Composer 主题](https://github.com/vran-dev/obsidian-composer)
- 配色移植自 @Sum-su 的 [yaobian-theme](https://github.com/Sum-su/yaobian-theme)（窑变），其颜色源自 [cherrycss.com](https://cherrycss.com) 主题画廊
- 任务复选框样式参考了 @Kepano 的 [Minimal 主题](https://github.com/kepano/obsidian-minimal)

<details>
<summary>开发说明（settings.yml + composer.css 双文件构建）</summary>

样式设置与 CSS 分离维护，由脚本合并生成最终文件：

- `settings.yml` —— Style Settings 声明（纯 YAML）
- `composer.css` —— 样式主体（纯 CSS）
- `build.mjs` —— 合并两者生成 `theme.css`

```bash
# 编辑 settings.yml / composer.css 后
npm run build        # 重新生成 theme.css
npm version patch    # 发版：自动构建并更新 manifest.json / versions.json
```

注意：`theme.css` 为构建产物，请勿手改其中的 YAML 头部。

</details>

---

<div align="center">

以 MIT 许可发布 · 窑变，釉色万千

</div>
