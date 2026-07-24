# Changelog

本项目遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 和[语义化版本](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Changed

- 将 `course-detail-image-generator` 从 Marketplace 插件改为可直接安装到个人技能目录的独立 Skill。
- 将原来的生成和无 PS 嵌图两个 Skill 合并为 `$course-detail-image-generator` 单一入口。
- 在 README 中增加可直接发送给 Agent 的安全更新指南。
- 强化无 PS 嵌图的严格几何模式：禁止把素材比例矩形误当完整开口，并对不可裁切的文字素材执行 `3%` 比例偏差阻断。

## [2.0.0] - 2026-07-23

### Added

- 增加仓库级校验脚本、GitHub Actions、贡献指南、安全政策和问题模板。
- 增加 MIT 许可证和完整的安装、使用、维护文档。

### Changed

- 将 `详情图生成` 的机器可读 Skill 名称标准化为 `generate-course-detail-images`，保留中文展示名和中文触发语义。
- 将插件版本提升至 `2.0.0`。显式调用语法由 `$详情图生成` 变为 `$generate-course-detail-images`。
- 重写 README，使其同时面向使用者和维护者。

## [1.0.0] - 2026-07-22

### Added

- 首次发布 `course-detail-image-generator` 插件。
- 包含 `详情图生成` 和 `embed-real-images-no-ps` 两个 Skills。
- 增加团队 marketplace、安装说明和技能文件校验和。

[Unreleased]: https://github.com/BenkyoEveryday/course-detail-image-skills/compare/v2.0.0...HEAD
[2.0.0]: https://github.com/BenkyoEveryday/course-detail-image-skills/compare/v1.0.0...v2.0.0
[1.0.0]: https://github.com/BenkyoEveryday/course-detail-image-skills/releases/tag/v1.0.0
