# App Icon Designer

一个面向 Codex 的应用图标设计技能：先理解项目，再选择一个清晰的实物隐喻，生成图标、检查小尺寸辨识度，并按目标平台完成适配。

A Codex skill for designing app icons from repository context, refining a single concrete metaphor, checking small-size legibility, and adapting assets to the target platform.

## 特点

- 读取项目说明、现有界面配色和图标资源，让图标贴合产品。
- 以一个主要物体表达产品，避免堆叠符号。
- 分别打磨轮廓和材质，检查 1024、128、32 像素下的效果。
- 考虑 Tauri、Electron、原生 Apple、Windows 和 PWA 的输出要求。
- 单文件技能，无附带脚本或参考文件依赖。

实际图像生成需要运行环境提供图像生成能力；没有该能力时，技能会提供提示词和集成方案。

## 安装

在 Codex 中输入：

```text
使用 skill-installer 安装 https://github.com/Hessel2333/app-icon-designer 中的技能，SKILL.md 位于仓库根目录。
```

也可以将本仓库的 `SKILL.md` 复制到 `$CODEX_HOME/skills/app-icon-designer/SKILL.md`。未设置 `CODEX_HOME` 时，默认目录为 `~/.codex/skills/app-icon-designer/`。

私有仓库需要使用有访问权限的 GitHub 账号。安装后，在下一轮对话中调用技能。

## 使用

在目标应用的项目目录中运行 Codex，输入：

```text
$app-icon-designer 给这个项目设计并生成一个 app icon，先读仓库再决定视觉隐喻。
```

也可以明确平台或设计约束：

```text
$app-icon-designer 为这个 Tauri 项目设计一个 1024×1024 图标，沿用当前 UI 配色，只生成一个候选方案。
```

技能默认先输出候选图标；明确要求替换或安装图标时，才会修改项目中的生产图标资源。

## 文件

- [SKILL.md](SKILL.md)：完整技能定义和工作流程。

本技能提供设计与检查流程；最终图标仍需在实际尺寸和目标平台中检查。
