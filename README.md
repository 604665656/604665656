# 604665656

做小工具的。桌面端、单文件网页游戏、数据看板，基本都是自己用得上才动手做。

**当前在弄**：哈士喵纸娃娃台 —— 一个本地跑的角色换装编辑器，[在线试试](https://604665656.github.io/hashimiao-paperdoll/)。
**怎么干活**：每个项目一本开发日记，记「要解决什么 / 怎么做的 / 验证 / 坑」，四个小节缺一不可。

---

## 项目看板

进度都挂在 GitHub Projects 上，不写在 README 里（README 会过期，看板不会）。

| 看板 | 项目 | 状态 |
|---|---|---|
| [哈士喵纸娃娃台 · 路线图](https://github.com/users/604665656/projects/2) | 11 层骨架 / 换装 / 八向帧 / 导出 | 8 项，1 个 P0 |
| [汽水音乐工具集 · 路线图](https://github.com/users/604665656/projects/9) | 18 个仓库的统一维护 | 4 项 |
| [wqn · 上下五千年 路线图](https://github.com/users/604665656/projects/3) | 单文件历史页游 | 2 项 |
| [清聪节奏 · 路线图](https://github.com/users/604665656/projects/4) | 单文件 Web 音游引擎 | 2 项 |
| [B站关注管理台 · 路线图](https://github.com/users/604665656/projects/5) | Electron 桌面版 | 2 项 |
| [live-copilot · 路线图](https://github.com/users/604665656/projects/6) | 弹幕游戏 AI 导演 | 2 项 |
| [skyworth 8S03 物理按键 · 路线图](https://github.com/users/604665656/projects/8) | 电视按键映射 | 2 项 |
| [若辰曲库 × Toy 小游戏 · 路线图](https://github.com/users/604665656/projects/7) | 匹配体系与生成物 | 2 项 |

优先级只有三档：**P0** 现在就做 / **P1** 下一批 / **P2** 有空再说。

---

## 哈士喵纸娃娃台

[![在线试玩](https://img.shields.io/badge/在线试玩-Pages-5cc8ff)](https://604665656.github.io/hashimiao-paperdoll/)
[![仓库](https://img.shields.io/badge/源码-hashimiao--paperdoll-181717?logo=github)](https://github.com/604665656/hashimiao-paperdoll)
[![原始稿](https://img.shields.io/badge/原始稿-314%20文件%20%2F%20180MB-ffb454)](https://github.com/604665656/hashimiao-asset-archive)

本地纸娃娃编辑器，纯前端无后端。操作模型参照《冒险岛》纸娃娃 4.0 的交互逻辑（只复刻操作方式，素材全部自有）。

- 11 层骨架合成，逐层独立透明度，眨眼 / 尾巴 / 歪头挂在固定支点上做局部变换
- 双渲染模式：正面分层（可无限换装）+ 八向帧（8 方向 × 4 帧，160×190）
- 一键导出：PNG 单图 / 8×4 雪碧图 / 11 层分层图
- 存档、base64 搭配码、深链参数（`?tab=&mode=&dir=&frame=&suit=`）

配套三套 Python 工具：截图批量入库（泛洪去背 + 连通域切图 + 归一化）、素材体检（尺寸 / alpha / 命名 / 缺件，47 项）、参考卡生成（头身比 / 衣褶 / 八向骨架比例）。

原始生成稿另存一份：[**hashimiao-asset-archive**](https://github.com/604665656/hashimiao-asset-archive)
—— 从元宝客户端缓存里抢救出的 304 张原图 + 桌面散件，共 314 个文件 / 180MB，
带 sha1 清单和图廊（[在线看](https://604665656.github.io/hashimiao-asset-archive/)）。

---

## 汽水音乐工具集

18 个仓库，一套东西：1 个插件宿主 + 1 个公共内核 + 2 个独立工具 + 14 个插件。装、停用、更新、回滚、卸载都走宿主，插件之间互不干扰。

| | |
|---|---|
| [qishui-host](https://github.com/604665656/qishui-host) | 插件宿主：安装 / 停用 / 更新 / 回滚 / 卸载 |
| [qishui-core](https://github.com/604665656/qishui-core) | 公共内核，无 UI |
| [qishui-dashboard](https://github.com/604665656/qishui-dashboard) 🔒 | 数据看板：本地抓取 + 离线看板 + 双 EXE |
| [qishui-music-automation](https://github.com/604665656/qishui-music-automation) 🔒 | 增长自动化：生成 + 风格画像 + 音频客观分析闭环 |

插件（每个都能独立运行、独立登录、独立发版）：

| 插件 | 做什么 | 插件 | 做什么 |
|---|---|---|---|
| [account](https://github.com/604665656/qishui-plugin-account) | 账号与登录 | [publish](https://github.com/604665656/qishui-plugin-publish) | 发布 |
| [board](https://github.com/604665656/qishui-plugin-board) | 数据看板 | [resident](https://github.com/604665656/qishui-plugin-resident) | 常驻守护 |
| [coldstart](https://github.com/604665656/qishui-plugin-coldstart) | 冷启动流量 | [revenue](https://github.com/604665656/qishui-plugin-revenue) | 平台与收益 |
| [dupscan](https://github.com/604665656/qishui-plugin-dupscan) | 歌词查重 | [review](https://github.com/604665656/qishui-plugin-review) | 复盘 |
| [export](https://github.com/604665656/qishui-plugin-export) | 导出音频 | [selftest](https://github.com/604665656/qishui-plugin-selftest) | 环境自检 |
| [lyricvideo](https://github.com/604665656/qishui-plugin-lyricvideo) | 歌词视频 | [studio](https://github.com/604665656/qishui-plugin-studio) | 编辑工作台 |
| [example-hello](https://github.com/604665656/qishui-plugin-example-hello) | 最小示例 / 开发模板 | [sync](https://github.com/604665656/qishui-plugin-sync) | 数据同步 |

---

## 单文件网页游戏

两个都是「一个 HTML 拷走就能玩」，不联网、无依赖、无构建产物依赖 CDN。

| 仓库 | 说明 |
|---|---|
| [wqn](https://github.com/604665656/wqn) | **上下五千年 · 无尽编年** —— 离线单文件历史分支页游。126 个文件，`node build.js` 出单文件 |
| [qingcong-rhythm](https://github.com/604665656/qingcong-rhythm) | **清聪节奏** —— 4 轨下落音游引擎，音频分析自动谱面，带 B站 Toy 平台层（排行榜 / 云存档 / 体力） |

都是单文件，所以最容易悄悄变大 —— 两个都挂了「构建后校验产物体积」的议题在看板上。

---

## 桌面工具

| 仓库 | 说明 |
|---|---|
| [bili-relation-manager](https://github.com/604665656/bili-relation-manager) | **B站多账号关注管理台**（Electron）：清理单向关注 / 回粉 / 搜索找目标 / 无人值守自愈 |
| [live-copilot](https://github.com/604665656/live-copilot) | **弹幕游戏 AI 导演**：读弹幕与画面，决定下一步剧情往哪走 |
| [ruochen-toy-games](https://github.com/604665656/ruochen-toy-games) 🔒 | **若辰曲库（3292 首）× B站 Toy 小游戏**：匹配体系、适配看板、12 周规划与预测模型 |

---

## 别的

| 仓库 | 说明 |
|---|---|
| [skyworth-8s03-physkey](https://github.com/604665656/skyworth-8s03-physkey) | 让创维 8S03 / 42E600Y 电视的**机身物理按键**直接切 HDMI 输入源，不用摸遥控器。改系统按键映射有变砖风险，出问题可能开不了机 |

---

<sub>🔒 = 私有仓库，链接只对本人可见。看板都是公开的，可以直接看进度。</sub>
