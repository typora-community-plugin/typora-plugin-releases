# Typora Plugin Releases

English | [简体中文](./README.zh-CN.md)

A plugin list of [typora-community-plugin](https://github.com/typora-community-plugin/typora-community-plugin) for [Typora](https://typora.io).

## Marketplace Preview

![](https://fastly.jsdelivr.net/gh/typora-community-plugin/typora-plugin-releases@main/docs/assets/base.jpg)

## Publish a plugin

1. Create a tag (version, like `1.0.0`) for a git commit
2. Push commits and tags to Github
3. Run `pnpm run pack` to pack your plugin as `plugin.zip`
4. Draft a release in Github, related tag (version, like `1.0.0`), naming with version (like `1.0.0`)
5. Upload `plugin.zip` to the release — this exact asset name is what the stats workflow tracks
6. Edit this repo `community-plugins.json` (the other-language `community-plugins.*.json` files are translated automatically and do not need editing), adding plugin manifest like:

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

7. Open a pull request with the change; after merge, translations and stats are updated automatically by GitHub Actions — no further action needed.

### Manifest fields

| Field | Required | Description |
| --- | --- | --- |
| `id` | yes | Unique identifier, format `<author>.<plugin-name>`. |
| `name` | yes | Display name shown in the marketplace. |
| `author` | yes | Plugin author (GitHub username or display name). |
| `description` | yes | Short description; this is what gets translated into other languages. |
| `repo` | yes | GitHub repository of the plugin, format `<owner>/<repo>`. Used to pull release stats and link details. |
| `platforms` | yes | Supported platforms: any combination of `"win32"`, `"linux"`, `"darwin"`. |

## For users

- Browse plugins in the [Typora marketplace](https://github.com/typora-community-plugin/typora-community-plugin).
- To request a new plugin be listed, open an issue or follow [Publish a plugin](#publish-a-plugin) and submit a PR.
