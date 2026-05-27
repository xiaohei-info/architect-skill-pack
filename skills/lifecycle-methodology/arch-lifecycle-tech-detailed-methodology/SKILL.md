---
name: arch-lifecycle-tech-detailed-methodology
description: Use when an architect must run the detailed-design portion of technical
  design, preserve the full lifecycle-stage doctrine for detailed design, and define
  the concrete runtime, project, flow, data, interface, non-functional, security,
  recovery, hardware, and implementation-plan surfaces needed for execution.
version: 1.2.0
author: Architect Skill Pack
license: MIT
metadata:
  hermes:
    tags:
    - architect
    - lifecycle
    - technical-design
    - detailed-design
    - implementation
    related_skills:
    - arch-lifecycle-delivery
    - arch-lifecycle-tech-detailed-technical-arch-diagramming
    - arch-lifecycle-tech-detailed-core-flow-diagramming
    - arch-lifecycle-tech-overview-methodology
---


# Technical Detailed Methodology

## Overview

This skill serves the architect role's **技术方案设计 → 详细设计 方法论 skill**.

It is the second half of technical design and should only start on top of a stable overview design.

The detailed-design stage is now intentionally kept **leaner**:
- keep separate specialist companion skills only for the two highest-value recurring artifact classes
  - 技术架构图
  - 关键流程图 / 状态机
- keep the other detailed-design surfaces inside this methodology skill as part of one integrated detailed-design packet

That keeps the live skill family clearer and avoids over-splitting the stage into too many tiny children.

## When to Use

Use when:
- solution design and overview design have already been reviewed
- the architect must define concrete technical realization surfaces for implementation
- the task is about 技术架构、项目架构、关键流程、数据结构、接口、非功能需求、安全、备份恢复、风险、硬件、实施计划

## Canonical Stage Doctrine (Full Preservation)

| 详细设计 | 技术架构   | 系统设计中的功能通过什么技术栈实现？如何选型的？项目结构是什么样的？ <br>系统运行起来后，服务、进程、任务、调用链路如何协作，稳定性如何保障？<br><br>_依赖与组件等实现方式，基于需求调研中得到的业务解决方案，合理利用技术栈、工具链、中间件的组合、以实施落地为目的对该业务方案进技术细化_<br> | 技术架构图，示例如下： <br>![](../../../../illustrative-source/软件架构设计的生命周期-1779158661450.png)                                                                                                          |
|      | 项目架构   | 代码、模块、组件、依赖如何组织，如何保证可维护性与可扩展性？<br><br>*项目结构、模块分层、组件依赖、技术选型说明*                                                                                             | 项目架构图                                                                                                                                                                                     |
|      | 关键流程   | 有哪些关键业务流程？通过什么图表来体现？ <br><br>_不同角色不同阶段的处理过程，以及各种分支情况的条件及处理逻辑，要覆盖所有流程分支，不重不漏_                                                                              | 状态机，示例如下：  <br>![](../../../../illustrative-source/软件架构设计的生命周期-1779158733831.png)流程图，示例如下：<br>![](../../../../illustrative-source/软件架构设计的生命周期-1779158753327.png)                              |
|      | 数据结构   | 程序中流转的数据是怎么定义的？                                                                                                                                           |                                                                                                                                                                                           |
|      |        | 与外部系统交互的接口数据是怎么定义的？                                                                                                                                       |                                                                                                                                                                                           |
|      | 数据架构   | 需要什么样的数据、如何存储与使用？ <br><br>*存储到数据库中的表结构定义，主键、字段类型、字段含义、唯一键、索引等 *                                                                                           | ER图（drawio-skill / draw.io 源文件）                                                                                                                                                                            |
|      |        | 数据一致性、唯一性、索引设计、冷热分层、归档清理、备份恢复、敏感数据保护如何设计？                                                                                                                 | 数据约束说明                                                                                                                                                                                    |
|      | 系统接口   | 对外接口如何定义？ _入参、出参、幂等、异常、结果码、超时、重试、限流、鉴权、审计要求_                                                                                                              | 接口定义文档                                                                                                                                                                                    |
|      | 非功能性需求 | 有哪些系统监控、业务监控、数据监控需求？核心指标、告警阈值、通知方式、响应人、处理时限分别是什么？                                                                                                         | 监控告警清单                                                                                                                                                                                    |
|      |        | 吞吐、延迟、并发、容量目标分别是什么？压测口径、验收标准是什么？                                                                                                                          | 性能指标与压测方案                                                                                                                                                                                 |
|      |        | 是否需要限流、熔断、降级、隔离、容灾、扩缩容能力？故障时如何保证核心服务可用？                                                                                                                   | 高可用方案                                                                                                                                                                                     |
|      |        | 鉴权、授权、数据脱敏、密钥管理、审计留痕、防刷、防重、防越权分别如何设计？                                                                                                                     | 安全设计说明                                                                                                                                                                                    |
|      |        | 需要备份哪些数据？恢复点目标（RPO）与恢复时间目标（RTO）是什么？恢复流程如何验证？                                                                                                              | 备份恢复方案                                                                                                                                                                                    |
|      |        | 当前已知风险有哪些？触发条件、影响范围、预防措施、应急预案分别是什么？                                                                                                                       | 风险清单                                                                                                                                                                                      |
|      | 硬件需求   | 需要哪些、什么样的硬件部署服务？ _硬件、网络、机器、节点、拓扑等_                                                                                                                        |                                                                                                                                                                                           |
|      | 实施计划   | 人力安排、团队配置、开发周期、测试周期、联调周期等细项                                                                                                                               |                                                                                                                                                                                           |

## Architect Execution Layer

- make the system implementable, not only understandable
- keep runtime structure, code structure, dynamic flows, data structures, interfaces, and NFR controls distinguishable
- use separate artifacts when one view cannot answer all detailed questions cleanly
- do not hide reliability, recovery, or security assumptions in vague prose

## Recommended Detailed-Design Packet

### Keep as separate specialist skills
These two are worth separate live skills because they are recurring, visually intensive, and easy to confuse with neighboring artifact types:
- `arch-lifecycle-tech-detailed-technical-arch-diagramming`
- `arch-lifecycle-tech-detailed-core-flow-diagramming`

### Keep inside this methodology skill
These usually do **not** need separate live skills by default unless a future workload proves they recur independently often enough:
- 项目架构
- 数据结构 / 数据架构
- 系统接口
- 非功能性需求
- 安全 / 高可用 / 备份恢复 / 风险
- 硬件需求 / 实施计划

Reason:
- they are important surfaces
- but they are often better handled as one integrated detailed-design packet than as many tiny sibling skills
- splitting them too far makes the family harder to load and reason about

## Practical Subsections To Cover Inside This Stage

### 1. 项目架构
Answer:
- how code / modules / components / dependencies should be organized
- how maintainability and extensibility are protected structurally

### 2. 数据结构 / 数据架构
Answer:
- what data objects move through the program
- what external interaction structures look like
- what persistent structures exist
- what consistency / indexing / archival / backup / sensitive-data rules apply

### 2A. Cross-module boundary tightening rules (high-value review TODO pattern)
When iterating a subsystem detailed-design document from reviewer TODOs, do not only “answer the comment”; use the TODO to check whether a diagram, object, or flow leaked across module boundaries.

Default tightening rules:
- if a flow is documenting **ETL / pipeline execution**, keep **query/read-definition concerns out of that flow** unless the query layer is a direct runtime participant
- if a release / rollback diagram is about **family-definition or pipeline-definition switching**, name the downstream runtime precisely (for example, later pipeline batches / replay batches) rather than a vague cross-layer label like “query layer”
- if a control-plane object belongs to a higher module, move it back to that module’s document instead of letting the current module absorb it “for completeness”
- when a reviewer says “this looks like a higher-layer concern”, prefer **scope reduction** over adding more explanatory arrows

Typical examples worth preserving:
- `Family Definition` onboarding / release belongs to the ETL / pipeline side; `Read API Definition` belongs to the query-serving side unless the current module truly governs both
- a subsystem-level detailed design may mention adjacent layers for context, but its dynamic diagrams should still track the module that actually executes the path

### 2B. Transport envelope vs external payload-reference rule
Do not default queue/event examples to `payload_ref` object-storage indirection.

Prefer this order:
1. first design the collector / batcher so one queue message stays within the transport limit
2. keep the real payload inline in the event envelope when that is operationally reasonable
3. use a separate object-reference indirection only as an explicit oversized-payload exception path, not as the default shape

Why:
- it keeps the transport contract simpler
- it avoids inventing a second truth hop for ordinary messages
- it makes replay, inspection, and definition onboarding examples more concrete

If inline payload is chosen, still carry a digest / stable id for idempotency and audit.

### 2C. Analytical replica sync modeling rule
When a local or edge analytical replica can connect directly to the upstream warehouse, model the sync path as a **thin sync executor/config layer** first; do not over-design exporter/importer/file-hop stages unless they are actually required.

Preferred expression in detailed design:
- state clearly whether the replica is **full snapshot** or incremental
- state exactly which upstream layers/tables are mirrored (for example raw + stage + governed views)
- keep the executor role thin: credentials injection, attach/config, sync SQL/materialization, watermark recording
- keep the replica out of the public serving hot path unless it is truly the serving backend

### 3. 系统接口
Answer:
- inputs / outputs
- idempotency
- exceptions / result codes
- timeout / retry / rate-limit
- auth / audit requirements

### 4. 非功能性需求 / 安全 / 可靠性 / 恢复
Answer:
- monitoring / alerting
- throughput / latency / concurrency / capacity
- HA / resilience / degrade / isolation / DR
- authz / authn / masking / key management / audit
- backup / RPO / RTO / restore validation
- known risks and emergency handling

### 5. 硬件需求 / 实施计划
Answer:
- hardware / network / machine / node / topology assumptions
- staffing / team configuration
- development / testing / integration schedule details

## Companion Diagram / Artifact Skills

- `arch-lifecycle-tech-detailed-technical-arch-diagramming`
- `arch-lifecycle-tech-detailed-core-flow-diagramming`

## Practical handoff pattern: overview design → detailed design packet

When a subsystem already has an approved/usable 概要设计 and the next user ask is “start detailed design now”, prefer this execution order:

1. **Read the overview design first and inherit its fixed boundaries.**
   Do not rediscover the system from scratch unless the overview is clearly unstable.
2. **Check whether the target directory already contains child-module detailed-design placeholders.**
   If they exist but are empty or near-empty, do **not** rush to fill all child docs first.
3. **Write a subsystem-level detailed-design hub document first.**
   This hub should answer the cross-module questions that implementation cannot avoid:
   - runtime technical architecture
   - main data/control flows
   - core objects / envelopes / enums and their execution semantics
   - upstream/downstream integration list
   - auth / connection paths
   - NFR / rollback / observability / recovery baseline
4. **Co-locate the key diagrams with that hub document first.**
   At minimum, produce:
   - 技术架构图
   - 核心流程图
   Add state/data-flow views only when they reduce ambiguity.
5. **Only after the hub stabilizes, split into child module detailed-design docs.**
   This avoids writing four inconsistent module docs while the shared runtime model is still moving.
6. **When landing child docs into pre-created module folders, use explicit artifact names and migrate links cleanly.**
   Preferred pattern:
   - place each child doc inside its module directory
   - name it as `<module>-详细设计文档` when the workspace/user wants the artifact level made explicit
   - update the subsystem hub note to point to the new canonical child-doc names
   - leave the old bare-name placeholder note as a tiny redirect/stub instead of keeping an empty file or duplicating content

Why this pattern works:
- it preserves implementation-level concreteness without fragmenting the design too early
- it keeps shared contracts and runtime semantics in one place first
- it gives later module docs a stable parent packet to inherit from
- it avoids broken wiki links and avoids confusing a folder placeholder with the real module-level detailed-design artifact

## Runtime-backed product/control-plane mapping rule

When the product being detailed is **not the runtime itself**, but a business/control plane built on top of a mature runtime or web-console base, the detailed-design packet must explicitly contain **two distinct layers**:

### PRD / prototype demotion rule for this class of design

When a runtime-backed product already has:
- business-solution documents,
- overview technical design,
- and PRD / prototype materials,

treat them with a strict priority order for **detailed design**:
1. **business solution + overview design** define server-side truth, runtime boundaries, and object ownership
2. **verified code / runtime entry points** define what is actually reusable and callable
3. **PRD / prototype** is used only to check page completeness, user-visible flows, and whether major product-facing capabilities were missed

Do **not** directly lift PRD/prototype material such as:
- pseudo backend endpoints
- page-level field dictionaries
- speculative table names
- mock implementation notes
- page interaction wording that pretends to be runtime truth

into the detailed-design server contract unless that information is independently validated by the business solution, overview design, or code.

Safe use of PRD in detailed design:
- use it to verify functional-domain coverage
- use it to discover missing user-visible states or pages that the design has not yet explained
- use it to pressure-test whether the control-plane objects are complete

Unsafe use of PRD in detailed design:
- treating PRD example fields/interfaces as authoritative backend design
- allowing prototype/UI terms to silently redefine runtime objects
- letting page-level implementation hints override the already-approved server-side architecture

Review heuristic:
- if a detailed-design paragraph can no longer answer "which higher-level design or verified runtime fact makes this true?", it is probably PRD leakage and should be rewritten or removed.

### Reviewer-TODO handling rule for architecture/design documents

When the user reviews a design document and leaves inline TODO comments, do not only answer whether the comment is "reasonable". Classify each TODO into one of these buckets before changing the document:
- **runtime truth correction** — the current text conflicts with verified runtime/code behavior
- **layering correction** — the current text collapses Team Panel / Gateway / Runtime boundaries
- **object-model clarification** — two objects or flows are under-specified and need sharper semantics
- **terminology correction** — a name is misleading relative to the runtime mapping
- **business binding correction** — a business object is being incorrectly equated with an execution object or workflow

For each TODO, prefer the smallest fix that restores the correct layer boundary. In particular, be suspicious when:
- browser/WebUI internal endpoints are described as if they were the formal Team Panel -> Gateway contract
- external message-platform group-chat ingress is conflated with browser-native team collaboration
- a business solution object (for example an industry solution) is treated as identical to an execution workflow instead of a blueprint that may bind a collaboration template
- PRD-origin terms are used where the runtime-backed object model should be named instead

1. **Team Panel / control-plane layer**
   - complete functional-domain inventory
   - business objects and ownership boundaries
   - product-facing flows, states, and governance semantics
2. **Gateway / runtime-mapping layer**
   - how each business object maps to a concrete runtime object, file, task, session, job, or SDK entry point
   - which parts are direct reuse vs extension vs net-new build

Minimum coverage rule for this class of detailed design:
- for **each functional domain**, list the required feature points, not just the module name
- for **each business object**, state its control-plane truth, runtime counterpart, and the mapping rule between them
- cover both:
  - **static mapping** — e.g. employee -> profile, connector grant -> credential/env injection, skill grant -> skill/runtime visibility
  - **dynamic mapping** — e.g. private chat -> single-agent run entry, orchestration task -> kanban task + dispatcher path, loop mission -> cron job
- name the real backend/code entry points from source verification, not README-level inference
- classify every mapping as:
  - **existing directly reusable**
  - **reusable with extension**
  - **must be newly built by the product layer**

This rule is especially important when a mature web UI already exists. Do not collapse:
- the web workbench shell
- the product's business objects
- the gateway/runtime adapter
into one blurred module just because the code lives in one repo.

## Canonical document placement rule

When writing design documents inside an existing project/vault/repo, land the artifact in the project's **canonical design path first**. Do not draft into ad-hoc temp locations and report completion there unless the user explicitly asked for a scratch copy.

Default behavior:
- detect the project's real design/document directory first
- write the formal artifact to that canonical path
- if permission or tooling constraints force a temporary draft elsewhere, copy it into the canonical destination before claiming completion
- when both a scratch copy and canonical file exist, clearly state which one is authoritative

This prevents a common architect failure mode: doing the thinking correctly but leaving the team looking at the wrong file.

See also `references/runtime-backed-product-mapping.md` for a concrete pattern covering business-object -> runtime-object mapping on top of an existing runtime/web-console base.

## Diagram Set Selection Rule

Detailed design should not default to **one** big diagram plus prose.

Choose the minimum diagram set that removes implementation ambiguity:
- **技术架构图** for stable runtime structure, control plane vs execution plane, and major storage/query boundaries
- **核心流程图** for the main happy path and key exception branches
- **时序图** when reviewers need actor-by-actor ordering, timing, or lifecycle visibility across components
- **数据流 / 对象关系图** when confusion is really about what objects exist, which layer owns them, and how they move
- **状态机 / 回滚图** when correctness depends on state closure, active-version switching, compensation, or rollback semantics

Rule of thumb:
- if a reviewer could ask “but in what order do these components actually talk?” → add a sequence diagram
- if they could ask “what data/object is flowing here?” → add a data-flow/object relation diagram
- if they could ask “how does version switch / rollback actually close?” → add a state or rollback-focused diagram

Do not wait for the user to explicitly request each companion diagram when the ambiguity is predictable.

## Child-module detailed-design companion-diagram rule

When a subsystem-level detailed-design hub document already contains the top-level technical architecture, core flow, release/rollback, and data/object relationship visuals, do **not** mechanically duplicate a “技术架构图” inside every child-module detailed-design note.

Instead, choose child-module diagrams by the specific implementation ambiguity they remove:
- if the module risk is **step order / actor sequencing**, add a **module-level sequence diagram**
- if the module risk is **internal stage boundaries / branch closure**, add a **module-level flowchart or state/closure diagram**
- if the module risk is **object ownership / truth-vs-replica layering**, add a **module-level data-flow or layered object diagram**
- only add a child-module technical-architecture diagram when the module truly has enough internal runtime structure to justify its own stable architecture view

Default anti-pattern to avoid:
- one subsystem hub has a good top-level architecture diagram
- then every child module gets another smaller architecture diagram that repeats the same planes with renamed boxes
- result: visual duplication rises, but implementation ambiguity remains

Preferred child-module diagram choices by common module type:
- **collector / ingress modules**: collection-to-enqueue control flow, checkpoint/state-advance gates, oversize/failure closure
- **pipeline / execution modules**: single-item sequence diagram plus internal stage-flow / branch diagram
- **query / serving modules**: hot-path sequence/flow plus cold-path refresh/control-path diagram
- **storage / replica modules**: layered ownership / truth-store vs serving-store vs replica diagram

Fast review test:
- if the child-module figure still reads mostly like a reduced copy of the subsystem architecture, it is probably the wrong diagram
- if the figure lets an implementer answer “who runs first, where does version freeze, where does failure stop, which store is truth, which path is hot vs cold” in ~30 seconds, it is likely the right child-module companion artifact

## Naming Boundary For Detailed Design Artifacts

When the deliverable is a **system-level detailed design document**, name it as the system/subsystem detailed design artifact itself (for example `XX详细设计方案`) rather than a lower-level working label such as “子模块设计”.

Reserve names like “子模块设计” for true module-collection indexes, not for the canonical subsystem-level detailed design document.

## Common Pitfalls

1. **Over-splitting detailed design into too many tiny skills.**
   The detailed stage has many surfaces, but not every surface deserves its own always-live specialist skill.

2. **Reusing overview-level abstractions as if they were sufficient for implementation.**
   Detailed design must be concrete enough to guide execution.

3. **Treating NFR/security/recovery as optional appendices.**
   These are part of the real design, not postscript polish.

4. **Stopping after one general flow diagram.**
   When time-order, object ownership, or rollback semantics are central, one high-level flowchart is not enough.

4. **Delivering only one generic flowchart for a subsystem detailed design.**
   A subsystem-level detailed design often needs more than one visual artifact. Do not wait for the user to explicitly ask for sequence/data-flow/release-flow diagrams if the text still leaves runtime order, control-plane behavior, or object boundaries ambiguous.

5. **Naming the subsystem detailed-design master note too generically.**
   For vault/document delivery, prefer the canonical artifact name `《<子系统名>详细设计方案》` for the subsystem-level detailed-design master document. Do not publish the main detailed-design document under a generic working name such as `子模块设计` unless the user explicitly asked for that as a folder/index, because it confuses the artifact's level and role.

## Diagram Completeness Rule For Detailed Design

When writing a subsystem-level detailed-design document, proactively decide whether the packet needs companion diagrams beyond the top technical architecture figure. Use this default test:
- if the reader may ask **"运行时先后顺序是什么"** → add a sequence diagram
- if the reader may ask **"控制面对象和运行时对象怎么衔接"** → add a data/object-flow diagram
- if the reader may ask **"发布、切版本、回滚怎么发生"** → add a release/rollback sequence or flow diagram
- if one core flow chart cannot answer all three cleanly, split the visuals instead of overloading one figure

This is a default architect responsibility, not an optional embellishment to wait for user prompting.

## Verification Checklist


## Verification Checklist

- [ ] Detailed design clearly inherits from a stable overview design
- [ ] Runtime, project, flow, data, interface, and NFR surfaces are adequately covered
- [ ] Key protections and recovery assumptions are explicit
- [ ] Separate specialist skills are used only where the split really adds clarity
- [ ] The design is implementation-guiding, not only principle-asserting
