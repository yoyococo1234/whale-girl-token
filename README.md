# 🐋 小鲸鱼吃token（手机优先版）

一只会偷吃 token 的「小鲸鱼（DeepSeek 娘化）」互动网页 —— **手机优先响应式版本**。

## 玩法
- 🍚 面前的大碗装着 token，她正一口一口吃；碗里 token 量随顶部进度条同步减少
- 👆 点她 / 敲她（或按空格）→ 停下嘟嘴 3 秒；不点就继续吃
- 🥷 随机**偷偷吃**：先左右张望（💧），再快速「啊呜」一口（🍚）；在偷吃动作中点中 = **抓包 +1**
- 😇 没抓到 → token 真被吃掉一口（-4），她还装无辜
- 📝 被抓到 → 举起检讨书「**我再也不吃你的token了！**」
- 🎉 token 被吃光 → 「吃饱啦~」，点「再来一碗」重开
- 手机端支持震动反馈（Android）

## 手机适配做法
| 项目 | 方案 |
| --- | --- |
| 竖屏构图 | 场景整体居中（不再贴底留大片空白），人物宽度用满屏宽 |
| 等比缩放 | 碗 / 检讨书 / 特效全部用容器查询单位 `cqw`，跟着人物一起缩放，不存在错位 |
| 气泡位置 | 改为**流式占位**（在人物头顶、HUD 下方），不会压住进度条、不会跳布局 |
| 横屏/矮屏 | `@media (max-height:520px)` 单独降级：压缩 HUD、缩小场景、隐藏提示与页脚 |
| 刘海/手势条 | `viewport-fit=cover` + `env(safe-area-inset-*)` |
| 误触缩放 | `touch-action:manipulation` + 禁用双击缩放与长按选中 |
| 添加到桌面 | 提供 `manifest.webmanifest`，可像 App 一样全屏打开 |

## 本地运行
双击 `index.html` 即可，无需联网、无需服务器。

## 部署（GitHub Pages）
仓库 Settings → Pages → Source 选 `main` / root → Save，访问
`https://<用户名>.github.io/<仓库名>/`

## 实测尺寸
390×844、360×640、414×896、768×1024、844×390（横屏）均无溢出、无遮挡。

## 素材与版权
- 形象素材来自社区鲸鱼娘表情包（[dsh-whale-widget-plus](https://github.com/louke6572/dsh-whale-widget-plus)，MIT；二创 MeteorNOX，原设「溟月」·上善无形，CC BY-NC-SA 4.0）
- 仅作个人非商用娱乐用途，与 DeepSeek 官方无关