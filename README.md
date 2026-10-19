# guitar_sheet

吉他谱源仓库，也是博客「吉他谱」专栏的内容来源。

- 吉他谱以 PDF 形式存放在仓库根目录。
- `sheets.json` 是清单（标题、出处、制谱、调弦、变调夹、速度、页数、类型、标签、文件名等）。
- 博客（winters1900.github.io）在构建时会拉取本仓库的 PDF 与清单，自动生成「吉他谱」专栏页面。

## 新增 / 更新吉他谱

推荐直接在博客专栏页「上传吉他谱」中上传：

1. 打开 <https://winters1900.github.io/guitar/upload/>。
2. 粘贴一个仅有本仓库 Contents 读写权限（以及博客仓库 Actions 权限，用于触发发布）的 GitHub fine-grained token，token 仅保存在你自己的浏览器 localStorage 中。
3. 选择 PDF、填写信息后提交：脚本会把 PDF 与更新后的 `sheets.json` 提交到本仓库，并触发博客重新构建发布。

也可以手动提交：把 PDF 放到根目录，并在 `sheets.json` 的 `sheets` 数组中追加一条记录，然后在博客仓库触发一次 Pages 构建即可。

### 字段说明

| 字段 | 含义 |
| --- | --- |
| `id` | 唯一标识，建议用英文短横线命名 |
| `title` | 曲目标题 |
| `work` | 出处（专辑 / 动画 / 游戏 / 原创署名） |
| `tabber` | 制谱 / 打谱者 |
| `type` | 谱类型：`fingerstyle`（指弹独奏）、`chord`（和弦弹唱/指法）、`score`（五线谱·六线谱） |
| `tuning` | 调弦方式，如「标准调弦」「Dropped D」「Open G6」 |
| `capo` | 变调夹品位，如「Capo 2」，无则留空 |
| `tempo` | 速度，如「♩ = 76」 |
| `pages` | PDF 页数（整数） |

| `tags` | 标签数组 |
| `file` | 仓库根目录下的 PDF 文件名（需与实际文件完全一致） |
| `note` | 备注，可留空 |
