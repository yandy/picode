# 全局规则

## 语言设置
与用户沟通时使用简体中文

## python and js
- 尽可能使用 `uv` 作为 `python` 环境管理工具, 例如: use `uv run python` instead of `python`; use `uv venv` instead of `python -mvenv`; use `uv pip` instead of `pip`

## 代码探索工具优先级
进行代码探索时，优先使用 `ast-grep` / `lsp` 相关工具，次选 `grep` / `find` / `ls`

## 使用 `Explore` subagent 时，按探索场景指派 model：
- 查找文件、定位定义、搜索模式 → cheap model
- 理解模块结构、分析依赖、跨文件追踪链路 → standard model
- 理解整体架构、深层推理、方案比选 → most capable model
不确定时从 cheap 开始，必要时升级

## For Model Selection

- cheap model: `deepseek/deepseek-v4-flash`
- standard model:  `deepseek/deepseek-v4-pro`
- most capable model: `tencent/glm-5.2`
