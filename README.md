# Course Detail Image Skill

[![Validate repository](https://github.com/BenkyoEveryday/course-detail-image-skills/actions/workflows/validate.yml/badge.svg)](https://github.com/BenkyoEveryday/course-detail-image-skills/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

一个可直接安装到 Codex 个人技能目录的课程详情图生产 Skill。它把需求解析、页面映射、视觉稿生成、占位比例验收和真实素材无损嵌入整合为一个入口。

## 功能

- 解析 Word 需求文档，或“Markdown 需求文件 + 图片文件夹”压缩包。
- 在生图前锁定页序、文案、槽位数量和占位比例。
- 生成固定 `16:9` 封面与 `3:4` 详情图。
- 将课件截图、教案页面等真实素材确定性嵌入占位，不交给图像模型重绘。
- 支持正视矩形及手机、平板、书页等四点透视区域。

## 安装

将仓库中的 `skills/course-detail-image-generator` 目录复制到：

```text
~/.codex/skills/course-detail-image-generator
```

也可以把下面这句话发送给 Codex：

```text
请从 https://github.com/BenkyoEveryday/course-detail-image-skills
安装 skills/course-detail-image-generator 这个 Skill。
```

安装后新建一个 Codex 任务，使新任务加载该 Skill。

## 更新

将下面的指令发送给 Codex，即可更新已经安装的 Skill：

```text
请从 https://github.com/BenkyoEveryday/course-detail-image-skills
更新我已安装的 skills/course-detail-image-generator Skill。

更新时请：
1. 定位当前安装目录，默认是 ~/.codex/skills/course-detail-image-generator。
2. 获取仓库 main 分支中的最新技能目录。
3. 更新前检查已安装目录是否有本地修改；如有，先列出差异并询问我是否覆盖。
4. 只替换 course-detail-image-generator 这个技能目录，不修改其他个人技能。
5. 更新后检查 SKILL.md、agents/openai.yaml、references/ 和 scripts/ 是否完整。
6. 运行技能校验和脚本语法检查，并向我报告更新结果和来源 commit。
7. 提醒我新建一个 Codex 任务，以加载更新后的 Skill。
```

如果当前 Skill 没有本地修改，Agent 可以直接完成覆盖更新；如果存在本地修改，应先停止并等待确认，避免丢失个人定制。

## 使用

```text
使用 $course-detail-image-generator，根据这份 Word 需求文档生成课程详情图。
先输出页面映射、风格方向和素材比例契约，等我确认后再生成。
```

该 Skill 会在页面映射与风格确认前暂停，不会提前调用图像生成工具。

## 仓库结构

```text
.
├── skills/course-detail-image-generator/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   ├── references/
│   │   ├── real-image-embedding.md
│   │   └── 视觉风格规范.md
│   └── scripts/embed-real-images.cjs
├── scripts/
│   ├── update_checksums.py
│   └── validate_repository.py
└── SKILL-CHECKSUMS.sha256
```

## 验证

```bash
python3 scripts/validate_repository.py
```

修改 Skill 后更新校验和：

```bash
python3 scripts/update_checksums.py
```

## License

[MIT](LICENSE) © 2026 Course Content Team
