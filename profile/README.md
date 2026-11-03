# dream2physical

> **Physical AI / 具身智能方向的复现与实测工作区**：按编号段将上游开源模型 / 系统以独立目录引入，只做"引入 + 复现 + 中文解读"，上游源码以 submodule 引用、不 fork。本页面是纯索引——详细使用说明见各项目仓库内 `START_HERE.md → README.md → docs/`。

## 状态图例

状态反映项目自身的验证成熟度；clone 后需先 `git submodule update --init --recursive` 并按各项目文档重建环境方能复现。

- ✅ **已验证 / 可运行**：已有本地实跑输出，或轻量流程可直接跑通
- 🟡 **基础可用 / 部分验证**：核心功能可用，完整链路依赖模型、数据、硬件或外设
- ⚠️ **暂未验证 / 环境待定**：项目较重，受显存、模型体积、多卡或运行时长限制

## 1xx · 具身智能模型系列（VLA / 世界模型 / 具身基础模型）

| 仓库 | 用途 | 状态 |
| --- | --- | --- |
| [100-openVLA](https://github.com/dream2physical/100-openVLA) | OpenVLA 7B 视觉-语言-动作模型：MuJoCo 仿真推理 + LIBERO 评测 | ✅ |
| [101-pi-serial-models](https://github.com/dream2physical/101-pi-serial-models) | π0 / π0.5 与 ACT 策略训练与评估（lerobot）：ALOHA 双臂 + LIBERO 两条评测链路 | ✅ |
| [102-cosmos](https://github.com/dream2physical/102-cosmos) | NVIDIA Cosmos 世界模型（RoboLab + cosmos-framework）：视频预测 + 动作策略 | ✅ |
| [103-lingbot](https://github.com/dream2physical/103-lingbot) | Lingbot 系列：depth（深度补全）/ video（MoE 视频生成）/ world-v2（交互世界模型）/ vla-v2 | 🟡 |
| [104-unitreerobotics](https://github.com/dream2physical/104-unitreerobotics) | 宇树双子项目：UnifoLM-WMA 世界模型-动作交互推理 + unitree_rl_mjlab（mjlab + PPO）运动控制训练 | ✅ |
| [105-damo](https://github.com/dream2physical/105-damo) | 达摩院：RynnBrain 具身多模态理解 + RynnWorld-4D 世界模型 | 🟡 |

## 2xx · 非具身模型（LLM 基模 / 生成类）

| 仓库 | 用途 | 状态 |
| --- | --- | --- |
| [200-video](https://github.com/dream2physical/200-video) | ComfyUI + MiniMax 视频生成工作流 | ✅ |
| [201-physicalRSI](https://github.com/dream2physical/201-physicalRSI) | RoboRSI 机器人自进化多智能体 harness 讲解（Manager / Planner / Engineer / Reviewer + TSR 技能精炼，LIBERO 120 任务） | ⚠️ |

## 3xx · 真机部署 / 人形机器人 / 趣味本地复现

| 仓库 | 用途 | 状态 |
| --- | --- | --- |
| [300-robots](https://github.com/dream2physical/300-robots) | Motion 机器人运动框架（异构硬件统一抽象：9 家厂商真机驱动 + 12 款 MuJoCo 机械臂）+ PI0-UR5E 仿真 | 🟡 |
| [301-microduck](https://github.com/dream2physical/301-microduck) | Microduck 微型机械臂：Rust 板载运行时 + mjlab / PPO 训练 | ⚠️ |
| [302-kingkongrobotics](https://github.com/dream2physical/302-kingkongrobotics) | 金刚机器人 jumper 跳跃足式机器人（mjlab + rsl_rl） | ⚠️ |
| [303-mimic](https://github.com/dream2physical/303-mimic) | Uni-SuperMimic 复现：Unitree G1 全身运动跟踪（可微世界模型 RL），单张消费级 GPU 即可完成训练，配套中文解读文档 01–04 | ✅ |

## 5xx · 具身数据 infra（采集 / 重定向 / 遥操作）

| 仓库 | 用途 | 状态 |
| --- | --- | --- |
| [500-umr](https://github.com/dream2physical/500-umr) | UMR：人体动作 → 点云对应 → 机器人 qpos 重定向（LAFAN1 跳舞 → Unitree G1） | ⚠️ |
| [502-DexAgent](https://github.com/dream2physical/502-DexAgent) | DexAgent：人类操作视频 → 灵巧手轨迹 → 随机化多视角训练视频 | ⚠️ |
| [503-do-as-i-do](https://github.com/dream2physical/503-do-as-i-do) | Do as I Do：手物视频 6DoF 跟踪 → Sharpa Wave 重定向（MuJoCo Warp MPC）→ 双臂回放 | 🟡 |

## 编号与目录约定

- 顶层目录命名 `NNN-kebab-case`（专有名词保留原大小写）；编号段：**1xx** 具身模型、**2xx** 非具身模型、**3xx** 真机/人形/趣味复现、**4xx** 预留、**5xx** 数据 infra。
- 每个复现目标独立成仓库，自产文档放仓库内 `docs/<目标名>/`，文件名带 `0N-` 序号前缀按阅读顺序排列。
- 上游仓库一律以 `git submodule` 引用并锁定单个 commit；模型权重、venv、训练产物、演示视频等大文件不入库，按各项目文档在本地获取。

## 联系与许可

- TODO: 联系方式 / issue 指引
- TODO: 各仓库许可见其自身 README；上游源码版权归原项目所有
