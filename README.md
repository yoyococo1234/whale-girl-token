# 🐋 鲸鱼娘的吃token时间

一只会偷吃 token 的「鲸鱼娘（DeepSeek 娘化）」互动小网页。

## 玩法
- 🍚 她面前的大碗里装着 token，正一口一口吃（碗里的 token 会随顶部条一起变少）
- 👆 点她 / 敲她（或按空格）→ 她停下嘟嘴 3 秒；不点就继续吃
- 🥷 她会随机**偷偷吃**：先左右张望（💧），再快速「啊呜」一口（🍚）；在偷吃动作中点中 = **抓包 +1**
- 😇 没抓到 → token 真被她吃掉一口（-4），她还装无辜
- 📝 被抓到 → 她举起检讨书「**我再也不吃你的token了！**」
- 🎉 token 被吃光 → 「吃饱啦~」，点「再来一碗」重开

## 本地运行
直接双击 `index.html` 即可，无需联网、无需服务器（全部资源都在本地 `assets/`）。

## 部署成公开网页（推荐 GitHub Pages）
1. 在 GitHub 新建一个 Public 仓库（例如 `whale-girl-token`）
2. 把 `index.html` 和 `assets/` 文件夹（5 张 PNG）上传进仓库
3. 仓库 Settings → Pages → Source 选 `main` 分支 / root → Save
4. 等约 1 分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`

或用命令行（需先装 GitHub CLI）：
```bash
gh auth login
cd <本项目目录>
git init && git add . && git commit -m "鲸鱼娘吃token互动页"
gh repo create whale-girl-token --public --source=. --push
gh api repos/<你的用户名>/whale-girl-token/pages -f 'source[branch]=main' -f 'source[path]=/'
```

## 素材与版权
- 形象素材来自社区鲸鱼娘表情包（[dsh-whale-widget-plus](https://github.com/louke6572/dsh-whale-widget-plus)，MIT；二创 MeteorNOX，原设「溟月」·上善无形，CC BY-NC-SA 4.0）
- 仅作个人非商用娱乐用途，与 DeepSeek 官方无关