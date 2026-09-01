# Typora 插件发布仓库（Typora Plugin Releases）

[English](./README.md) | 简体中文

[typora-community-plugin](https://github.com/typora-community-plugin/typora-community-plugin) 面向 [Typora](https://typoraio.cn) 的插件列表。

## 市场预览

![](https://fastly.jsdelivr.net/gh/typora-community-plugin/typora-plugin-releases@main/docs/assets/base.jpg)

## 发布一个插件

1. 为某个 git commit 创建 tag（版本号，如 `1.0.0`）
2. 将 commits 和 tags 推送到 Github
3. 运行 `pnpm run pack`，将插件打包为 `plugin.zip`
4. 在 Github 上创建一个 release，关联该 tag（版本号，如 `1.0.0`），并以版本号命名（如 `1.0.0`）
5. 将 `plugin.zip` 上传到该 release —— 统计 workflow 追踪的就是这个固定资产名
6. 编辑本仓库的 `community-plugins.json`（其他语言的 `community-plugins.*.json` 会自动翻译，不需要编辑），添加插件 manifest，例如：

  ```json
  {
    "id": "author.plugin-name",
    "name": "Plugin Name",
    "author": "author",
    "description": "Plugin description.",
    "repo": "github-user/github-repo",
    "platforms": ["win32", "linux", "darwin"]
  }
  ```

7. 提交一个包含此变更的 pull request；合并后，翻译与统计数据会由 GitHub Actions 自动更新 —— 无需再做其他操作。

### Manifest 字段说明

| 字段 | 必填 | 描述 |
| --- | --- | --- |
| `id` | 是 | 唯一标识符，格式为 `<author>.<plugin-name>`。 |
| `name` | 是 | 在市场中展示的插件名称。 |
| `author` | 是 | 插件作者（GitHub 用户名或显示名）。 |
| `description` | 是 | 简短描述；该字段会被翻译成其他语言。 |
| `repo` | 是 | 插件的 GitHub 仓库，格式为 `<owner>/<repo>`。用于拉取 release 统计与链接详情。 |
| `platforms` | 是 | 支持的操作系统：可任意组合 `"win32"`、`"linux"`、`"darwin"`。 |

## 面向用户

- 在 [Typora 插件市场](https://github.com/typora-community-plugin/typora-community-plugin) 中浏览插件。
- 如需申请收录新插件，可提交 issue，或参照[发布一个插件](#发布一个插件)自行提交 PR。
