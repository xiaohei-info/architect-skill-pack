# architect-skill-pack

语言： [English](README.md) | [简体中文](README.zh-CN.md)

[![Release](https://img.shields.io/github/v/release/xiaohei-info/architect-skill-pack?display_name=tag)](https://github.com/xiaohei-info/architect-skill-pack/releases)
[![License](https://img.shields.io/github/license/xiaohei-info/architect-skill-pack)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/xiaohei-info/architect-skill-pack)](https://github.com/xiaohei-info/architect-skill-pack/commits/main)

**一套可复用、开源、面向架构工作的技能包：覆盖方案调研、解决方案设计、技术概要设计、详细设计、部署交付，以及各类架构图方法。**

这是一个**通用架构方法包**。任何 agent runtime、宿主系统或架构团队都可以使用。

当你的架构工作出现这些问题时，可以使用这个仓库：
- 需求还很模糊，就直接进入实现
- 业务方案、技术设计、部署运维被写成一团
- 图虽然很多，但每张图都没回答对问题
- 方案调研太浅，团队反复重复造轮子
- 详细设计不够具体，开发在没有清晰契约和流程的情况下开工

你可以按需采用：
- **单个 skill**
- **单个 bundle**
- **整套技能包**

## 采用后你应该获得什么

如果采用得当，你应该获得这些改进：
- 在架构工作开始前先明确当前所处阶段
- 更清晰地区分业务方案、系统架构、技术架构和部署交付产物
- 让不同图真正回答不同问题，而不是相互重复
- 让详细设计更接近可实现交付物，而不是停留在原则层
- 让方案推荐自带权衡、复用判断与验证路径

## 运行时适配性

任何 agent runtime、宿主系统或架构团队都可以使用这个技能包。

两种常见使用方式：
- **直接安装** — 支持 `SKILL.md` 目录加载的宿主可以直接安装
- **方法库** — 把每个 skill 作为可复用的架构 playbook，映射到自己的 prompt、command、planner 或 workflow 模型

具体适配方式见 [`docs/host-adaptation.md`](docs/host-adaptation.md)。

## 仓库包含什么

本仓库将 17 个架构角色 skill 整理为 3 个公开 bundle：

- **lifecycle-methodology**：架构生命周期分阶段交付方法
- **diagramming**：业务架构图、业务流程图、系统架构图、技术架构图、关键流程图等绘图方法
- **architecture-supplements**：DDD 边界建模、设计模式/重构、技术选型比较方法

## 推荐起步方式

### 如果你的架构工作经常在错误阶段开始
先看：
- `lifecycle-methodology/arch-lifecycle-delivery`
- `lifecycle-methodology/arch-lifecycle-demand-survey-methodology`

### 如果解决方案设计总是写不透
先看：
- `lifecycle-methodology/arch-lifecycle-solution-design-methodology`
- `diagramming/arch-lifecycle-solution-design-biz-flow-diagramming`
- `diagramming/arch-lifecycle-solution-design-biz-arch-diagramming`

### 如果技术设计经常只有原则，没有实现落点
先看：
- `lifecycle-methodology/arch-lifecycle-tech-overview-methodology`
- `lifecycle-methodology/arch-lifecycle-tech-detailed-methodology`
- `diagramming/arch-lifecycle-tech-detailed-core-flow-diagramming`
- `diagramming/arch-lifecycle-tech-detailed-technical-arch-diagramming`

### 如果技术选型经常沦为拍脑袋
先看：
- `architecture-supplements/technology-adoption-comparison`
- `architecture-supplements/ddd-domain-modeling-for-architecture`
- `architecture-supplements/design-patterns-and-refactoring`

## 安装与采用路径

### 路径 A：直接安装（支持 `SKILL.md` 的宿主）

如果你的宿主支持以 `SKILL.md` 为入口的目录式 skill 加载，可以直接安装。

### 前置条件

在安装之前，请确认：
- 宿主的 skill 库路径可用，或可以自行创建
- 你会复制**整个 skill 目录**，而不是只复制 `SKILL.md`

```bash
git clone https://github.com/xiaohei-info/architect-skill-pack.git
cd architect-skill-pack
mkdir -p <your-skill-library-path>
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery <your-skill-library-path>/
```

完整说明见 [`docs/adoption-guide.md`](docs/adoption-guide.md)。

### 路径 B：作为方法库使用

如果你的宿主不支持 `SKILL.md` 目录加载，可以把仓库作为方法库：

1. 选择目标 skill 目录
2. 阅读其中的 `SKILL.md` 以及相关 `references/` / `templates/`
3. 映射到宿主的等价机制：
   - 可复用 prompt / playbook
   - custom command
   - planner checklist
   - workflow / delegation 约束
4. 尽量把宿主特有的 wiring 放在公共 skill 之外

具体适配方式见 [`docs/host-adaptation.md`](docs/host-adaptation.md)。

## 这个技能包为什么有价值

这套技能包的核心不是“多几份 prompt”，而是把架构工作中最容易失真的部分沉淀成可复用方法：
- **先调研，再定方案**
- **按阶段产出，不把所有设计揉成一张图**
- **每种图回答不同问题**
- **详细设计要具体到可实现**
- **方案推荐必须写出权衡和验证路径**

## 相关文档

- [`AGENTS.md`](AGENTS.md)
- [`docs/bundles.md`](docs/bundles.md)
- [`docs/adoption-guide.md`](docs/adoption-guide.md)
- [`docs/host-adaptation.md`](docs/host-adaptation.md)
- [`docs/portability-notes.md`](docs/portability-notes.md)
- [`docs/source-map.md`](docs/source-map.md)

## 许可证

MIT
