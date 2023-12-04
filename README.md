# Typora Plugin Releases

A plugin list of [typora-community-plugin](https://github.com/typora-community-plugin/typora-community-plugin) for [Typora](https://typora.io).

## Marketplace Preview

![](https://fastly.jsdelivr.net/gh/typora-community-plugin/typora-plugin-releases@main/docs/assets/base.jpg)

## Publish a plugin

1. Create a tag (version, like `1.0.0`) for a git commit
2. Push commits and tags to Github
3. Run `pnpm run pack` to pack your plugin as `plugin.zip`
4. Draft a release in Github, related tag (version, like `1.0.0`), naming with version (like `1.0.0`)
5. Upload `plugin.zip` to release
6. Edit this repo `community-plugins.json`, adding plugin manifest like:

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
