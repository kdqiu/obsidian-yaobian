[中文](README_zh.md) | English

# 窑变 for Obsidian

**Yaobian** is a personalized fork of the [Composer](https://github.com/vran-dev/obsidian-composer) theme for Obsidian, which is designed for reading and writing comfortably.

## Fork Changes

Compared with upstream Composer:

- **Removed** the 「Ní 霓」 color scheme and all [Components](https://cp.cc1234.cc/) plugin related settings & styles.
- **Added 72 color schemes** (36 families × light/dark) ported from [yaobian-theme](https://github.com/Sum-su/yaobian-theme) (窑变), selectable via the `style settings` plugin.

## Color Schemes

> [!NOTE]
> Changing the color scheme requires the `style settings` plugin.

Built-in schemes (kept from upstream):

- Xiá 霞
- Sù 素
- Qīng 青

Ported from yaobian-theme (36 families, each with light & dark):

`chineseStyle` (25)

| | | | | |
| --- | --- | --- | --- | --- |
| 禅棕 `chan-zong` | 长安 `chang-an` | 春梅 `chun-mei` | 丹霞 `dan-xia` | 汉白玉 `han-bai-yu` |
| 湖光 `hu-guang` | 金镶玉 `jin-xiang-yu` | 流云 `liu-yun` | 琵琶 `pi-pa` | 青瓷 `qing-ci` |
| 青花 `qing-hua` | 青雾 `qing-wu` | 汝窑蓝 `ru-yao-lan` | 汝窑绿 `ru-yao-lv` | 山水 `shan-shui` |
| 素宣 `su-xuan` | 天水 `tian-shui` | 宣纸 `xuan-zhi` | 雁灰 `yan-hui` | 烟雨 `yan-yu` |
| 胭脂 `yan-zhi` | 羊皮纸 `yang-pi-zhi` | 窑火 `yao-huo` | 玉石 `yu-shi` | 紫陶 `zi-tao` |

`others` (11)

| | | | | |
| --- | --- | --- | --- | --- |
| Claude | Dopamine | Dracula | 歌蕾蒂娅 `gladiia` | Mint |
| 莫奈 `mo-nai` | 暮山紫 `mu-shan-zi` | 奶茶 `nai-cha` | Peppa | Pulse `pulse-interactive` |
| Vitesse Soft `vitesse-soft` | | | | |

## Thanks

- This fork is based on the [Composer theme](https://github.com/vran-dev/obsidian-composer) by @vran.
- The ported color palettes come from [yaobian-theme](https://github.com/Sum-su/yaobian-theme) (窑变) by @Sum-su, whose colors trace back to the [cherrycss.com](https://cherrycss.com) gallery.
- Task checkbox is referenced from [Minimal Theme](https://github.com/kepano/obsidian-minimal) which is a great theme for Obsidian build by @Kepano.

## Development Workflow (settings.yml + composer.css Split)

This theme separates the Style Settings YAML header from the CSS for better editor support.

Files:

- `settings.yml` – Pure YAML (no wrapping comment). Edit Style Settings options here.
- `composer.css` – Pure CSS body (without the initial `/* @settings ... */` block).
- `build.mjs` – Build script that merges the two into `theme.css`.

Usage:
1. Edit style settings in `settings.yml`.
2. Edit styles in `composer.css`.
3. Run `npm run build` to generate `theme.css`.
4. Load or distribute `theme.css` as the final theme file.

Release Flow:
`npm version patch|minor|major` will automatically:
1. Run `preversion` (which triggers `npm run build`).
2. Bump version and stage `manifest.json`, `versions.json`, and `theme.css`.

Notes:
- Do NOT manually edit the YAML inside `theme.css`; it will be regenerated.
- Only add/change settings in `settings.yml`.
- The build script strips an optional leading comment block from `composer.css` before concatenation.
