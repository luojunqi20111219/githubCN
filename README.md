# GithubCN

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/luojunqi20111219/githubCN)

GitHub 浏览器中文汉化插件，为 GitHub 提供完整的简体中文界面支持。

> [!NOTE]
> 本项目是基于原作者 **[JQiue/githubCN](https://github.com/JQiue/githubCN)** 的分支维护版本。由于原版已较少更新，本项目进行了多处翻译修复，并新增了**动态正则匹配翻译功能**以汉化实时加载的数据。

---

## ✨ 新特性与优化 (New Features & Optimizations)
1. **完善翻译**：补充了大部分原版缺失的侧边栏菜单（Home、All issues、All repositories、MCP registry、Top repositories）、操作菜单（Agents、Actions、Security and quality）、设置选项和页脚链接等。
2. **修复翻译错误**：例如将页脚错误的 `Terms ➔ 团队` 纠正为 `Terms ➔ 服务条款`。
3. **动态正则匹配汉化 (Dynamic Translation)**：支持对时间（如 `2 weeks ago` ➔ `2 周前`）、仓库统计数据（如 `9 stars` ➔ `9 颗星`、`1 fork` ➔ `1 次复刻`、`1 Tag` ➔ `1 个标签`）等动态加载的内容进行实时翻译。

---

## 📦 安装与使用 (Installation)

### 方式 1：手动安装（开发者模式，推荐）
1. 在本仓库上方点击 **Code ➔ Download ZIP** 下载源码并解压到本地。
2. 打开 Chromium 浏览器（如 Chrome、Edge 等），在地址栏输入 `chrome://extensions/`（或 `edge://extensions/`）并回车。
3. 开启右上角的 **「开发者模式」 (Developer mode)**。
4. 点击左上角的 **「加载已解压的扩展程序」 (Load unpacked)**，选择刚刚解压的文件夹（选中包含 `manifest.json` 的目录）。
5. 安装完成，打开 [GitHub](https://github.com/) 即可看到汉化效果。

### 方式 2：通过应用商店安装（如有发布）
* [Edge 加载项商店](https://microsoftedge.microsoft.com/addons/detail/githubcn/onlodfoebaobhmlhgcbddjngjbkdbfaj) （注：此链接为原作者上架版本，本分支持续优化的内容需要手动安装或等待本分支发布）。

---

## 🛠️ 如何贡献/补充翻译词条？ (How to Contribute)

所有的翻译内容都在 [src/js/content.js](src/js/content.js) 中：

* **静态文本翻译**：在 `allData` 数组中添加匹配的键值对：
  ```js
  const allData = [
    [`English`, `中文`],
  ];
  ```
* **动态/数值翻译**：在 `regexData` 数组中添加正则表达式：
  ```js
  const regexData = [
    [/(\d+)\s+stars?/i, '$1 颗星'],
  ];
  ```

修改代码后，在扩展程序页面点击本插件卡片右下角的 **「刷新 (↻)」按钮** 即可立即在页面上看到效果。

---

## 📄 开源许可证 (License)
本项目采用 **GNU General Public License v3** 开源协议授权，请参阅：
* [LICENSE 英文原文 (Official English Version)](LICENSE)
* [LICENSE.zh-CN 中文说明 (Unofficial Chinese Preamble & Summary)](LICENSE.zh-CN.md)
