<div align="center">

# 流式多模态理解与交互

**持续感知。有效记忆。及时交互。**

[English](README.md) | **简体中文**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![论文数](https://img.shields.io/badge/papers-110-blue)
![更新日期](https://img.shields.io/badge/updated-2026--10--21-green)
[![欢迎贡献](https://img.shields.io/badge/contributions-welcome-orange)](CONTRIBUTING.md)

</div>

我们的目标是让 AI 理解不断变化的世界：持续接收**文字、图像、视频和音频**，记住重要信息，并通过**文字和语音**回应。系统应随着新观测更新理解，仅依据当前及此前的证据，在可控的记忆开销和响应延迟下运行。

[理解](#理解) · [记忆](#记忆) · [跨模态同步](#跨模态同步) · [在线推理与交互](#在线推理与交互) · [评测基准](#评测基准)

日期为预印本首次提交的月份；各表按时间倒序排列。

## 理解

**发生了什么，如何理解场景、物体、空间关系、声音和语言？**

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.09 | [**MOBA-VL**](https://arxiv.org/abs/2609.38428) | 利用游戏事件记录监督多轮强化学习，生成与事件对齐的实时电竞解说。 | [项目](https://moba-vl.github.io/) |
| 2026.09 | [**TempoGround**](https://arxiv.org/abs/2609.02359) | 跟踪对象的存在状态与身份，实现连续一致的二维和三维语言定位。 | — |
| 2026.08 | [**Stream3Dv2**](https://arxiv.org/abs/2608.21136) | **感知组件：** 融合颜色、深度与语义信息，支持流式开放词汇三维分割。 | [作者仓库](https://github.com/SubmissionsIn/Stream3D) |
| 2026.08 | [**StreamOPD**](https://arxiv.org/abs/2608.16320) | 训练时利用额外时空线索进行蒸馏，推理时仅依赖已观测信息。 | [代码](https://github.com/UniX-AI-Lab/StreamOPD) · [项目](https://unix-ai-lab.github.io/StreamOPD/) |
| 2026.07 | [**VideoChat3**](https://arxiv.org/abs/2607.14935) | 结合时空视觉编码与自适应分辨率，支持通用流式视频理解。 | [代码](https://github.com/MCG-NJU/VideoChat3) · [项目](https://mcg-nju.github.io/VideoChat3/) |
| 2026.06 | [**Stream3D-VLM**](https://arxiv.org/abs/2606.06891) | 增量融合几何先验，支持在线视频的空间推理与目标定位。 | [代码](https://github.com/hanxunyu/Stream3D-VLM) · [项目](https://stream3d-vlm.github.io/) |
| 2026.05 | [**StreamOV**](https://arxiv.org/abs/2605.25621) | 通过容量受限的音视频证据记忆，支持在线推理与主动回应。 | — |
| 2026.04 | [**Qwen3.5-Omni**](https://arxiv.org/abs/2604.15804) | 结合分块音视频感知、时间定位描述与语音回复。 | [官方介绍](https://qwen.ai/blog?id=qwen3.5-omni) |
| 2026.03 | [**ColorTrigger**](https://arxiv.org/abs/2603.22466) | 持续保留灰度观测，在颜色信息有价值时请求彩色输入。 | [项目](https://lvgd.github.io/ColorTrigger/) |
| 2026.03 | [**S2GS**](https://arxiv.org/abs/2603.14232) | **感知组件：** 持续更新三维语义场，并保持实例身份一致。 | [项目](https://stdcoutzrh.github.io/projects/s2gs/) |
| 2026.03 | [**OmniStream**](https://arxiv.org/abs/2603.12265) | 视觉骨干仅依赖已观测输入，学习时空及语言对齐表征。 | [代码](https://github.com/Go2Heart/OmniStream) |
| 2026.02 | [**ART-STVG**](https://arxiv.org/abs/2602.23294) | **顺序定位：** 定位语言描述对应的对象和事件边界，尚未达到实时处理。 | [仓库](https://github.com/HengLan/ART-STVG) |
| 2025.12 | [**Streamo**](https://arxiv.org/abs/2512.21334) | 统一学习在线动作理解、事件描述、时间定位与视频问答。 | [代码](https://github.com/maifoundations/Streamo) · [项目](https://jiaerxia.github.io/Streamo/) |
| 2025.11 | [**LiveStar**](https://arxiv.org/abs/2511.05299) | 增量对齐视频与语言，动态决定回应或静默，保持解说连贯。 | [代码](https://github.com/sotayang/LiveStar) |
| 2025.10 | [**video-SALMONN S**](https://arxiv.org/abs/2510.11129) | 将持续音视频观察整合为快速权重记忆，支持长时理解。 | [代码分支](https://github.com/bytedance/SALMONN/tree/video-salmonn-S) |
| 2025.10 | [**StreamingVLM**](https://arxiv.org/abs/2510.09608) | 对齐重叠片段训练与缓存推理，持续理解视频并生成解说。 | [代码](https://github.com/mit-han-lab/streaming-vlm) |
| 2025.09 | [**OpenHOUSE**](https://arxiv.org/abs/2509.12145) | 检测动作边界，并在多个时间尺度上描述事件。 | — |
| 2025.09 | [**Time-Scaling SSMs**](https://arxiv.org/abs/2509.03426) | 在片段间传递状态，在线定位事件并生成事件描述。 | — |
| 2025.08 | [**OVG-HQ**](https://arxiv.org/abs/2508.11903) | 根据文字、图像、视频及组合查询，在线定位视频片段。 | [代码与数据](https://github.com/maojiaqi2324/OVG-HQ) |
| 2025.04 | [**StreamFormer**](https://arxiv.org/abs/2504.20041) | 流式视频编码器仅用已观测输入，联合学习动作语义、时间定位和空间分割。 | [代码](https://github.com/Go2Heart/StreamFormer) · [项目](https://go2heart.github.io/streamformer/) |
| 2025.04 | [**TimeChat-Online**](https://arxiv.org/abs/2504.17343) | 去除冗余视觉 token，保留新到帧中的变化。 | [代码](https://github.com/yaolinli/TimeChat-Online) · [项目](https://timechat-online.github.io/) |
| 2025.04 | [**LiveCC**](https://arxiv.org/abs/2504.16030) | 从带时间戳的转录文本学习时间对齐，用于实时视频解说。 | [代码](https://github.com/showlab/livecc) · [项目](https://showlab.github.io/livecc/) |
| 2025.03 | [**StreamMind**](https://arxiv.org/abs/2503.06220) | 持续提取事件特征，并在相关事件发生时触发语言推理。 | [代码与数据](https://github.com/xinding-bot/StreamMind) |
| 2024.06 | [**VideoLLM-online**](https://arxiv.org/abs/2406.11816) | 学习随视频到来开展流式对话，并判断回应时机。 | [代码](https://github.com/showlab/videollm-online) |

<details open>
<summary>理解相关基础工作</summary>

离线视听推理、通用听觉与基于图像的语音交互。

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.09 | [**OmniReasoning**](https://arxiv.org/abs/2609.39490) | 通过证据线索和模态分解自蒸馏训练音视频联合推理。 | [代码](https://github.com/PKU-VaLuE-Lab/OmniReasoning) · [项目](https://pku-value-lab.github.io/OmniReasoning-Homepage/) |
| 2026.08 | [**ST-Omni-R1**](https://arxiv.org/abs/2608.09435) | 结合全景画面理解声源身份、位置、距离和运动轨迹。 | — |
| 2026.07 | [**SALMONN-2**](https://arxiv.org/abs/2607.17079) | 融合自监督音频多层特征，理解语音、声音、音乐与副语言信息。 | [代码分支](https://github.com/bytedance/SALMONN/tree/salmonn2) |
| 2026.05 | [**LatentOmni**](https://arxiv.org/abs/2605.22012) | 在文字推理中交织时间对齐的音视频潜在状态。 | — |
| 2026.04 | [**Nemotron 3 Nano Omni**](https://arxiv.org/abs/2604.24954) | 压缩时序视觉词元，高效理解长音视频内容。 | [模型](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16) |
| 2025.10 | [**OmniVinci**](https://arxiv.org/abs/2510.15870) | 通过相对与绝对时间编码学习对齐的音视频表示。 | [代码](https://github.com/NVlabs/OmniVinci) · [项目](https://nvlabs.github.io/OmniVinci/) |
| 2025.06 | [**video-SALMONN 2 / 2+**](https://arxiv.org/abs/2506.15220) | 优化忠实完整的音视频事件描述，并将收益迁移到问答。 | [代码](https://github.com/bytedance/video-SALMONN-2) |
| 2025.03 | [**MoshiVis**](https://arxiv.org/abs/2503.15633) | 通过门控视觉适配，为全双工语音对话加入图像理解。 | [代码](https://github.com/kyutai-labs/moshivis) |

</details>

## 记忆

**随着输入流增长，系统应保留、更新和检索哪些信息？**

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**MaLoW**](https://arxiv.org/abs/2610.22070) | 将长期流式历史存入大小固定、持续更新的 LoRA 权重。 | [代码](https://github.com/dragonlzm/MaLoW) · [项目](https://dragonlzm.github.io/MaLoW/) |
| 2026.10 | [**DeltaStreamer**](https://arxiv.org/abs/2610.19849) | 将视觉变化记为文字，检索记忆并回放证据。 | [代码](https://github.com/BBBBchan/DeltaStreamer) · [项目](https://bbbbchan.github.io/DeltaStreamer/) |
| 2026.10 | [**FlashBack**](https://arxiv.org/abs/2610.01192) | 通过独立缓存通路控制历史回忆，保留对当前场景的感知。 | — |
| 2026.09 | [**MEMO**](https://arxiv.org/abs/2609.38900) | 通过实体感知索引，按需检索独立归档的高分辨率视觉证据。 | [代码](https://github.com/Cecilia384/MEMO) |
| 2026.09 | [**EGSD**](https://arxiv.org/abs/2609.36803) | 基于事件的自蒸馏，维持增量记忆对实体的覆盖。 | — |
| 2026.09 | [**MemEvo**](https://arxiv.org/abs/2609.36581) | 在资源预算内，通过程序搜索发现仅依赖已观测输入的记忆机制。 | — |
| 2026.09 | [**SVMemAgent**](https://arxiv.org/abs/2609.18540) | 学习在查询到来前选择和替换记忆帧。 | — |
| 2026.09 | [**MemForest**](https://arxiv.org/abs/2609.08273) | **智能体记忆：** 通过事件树压缩记忆，并引导时序检索。 | [代码](https://github.com/Celina-love-sweet/MemForest) |
| 2026.09 | [**CoFiE**](https://arxiv.org/abs/2609.03675) | 编码前筛选有新信息的帧，再精细筛选与查询相关的证据。 | — |
| 2026.09 | [**ShallowStream**](https://arxiv.org/abs/2609.02780) | 构建浅层缓存索引，选择性检索历史证据。 | [代码](https://github.com/CURRENTF/ShallowStream) |
| 2026.08 | [**StreamScout**](https://arxiv.org/abs/2609.00291) | 按需从文字时间线转向详细视觉证据，调整记忆访问。 | — |
| 2026.08 | [**StreamEMS**](https://arxiv.org/abs/2608.27881) | 结合语义与先验信息，重组并更新视觉记忆。 | — |
| 2026.08 | [**StreamFlow**](https://arxiv.org/abs/2608.10949) | 过滤冗余观测，并在生成回答时检索视觉潜在表征。 | — |
| 2026.07 | [**FOLIO**](https://arxiv.org/abs/2607.13298) | 维护以实体为中心、关联原始视觉证据的语义记忆。 | — |
| 2026.06 | [**SelectStream**](https://arxiv.org/abs/2606.16353) | 在容量固定的潜在记忆中，结合惊异度驱动写入与图检索。 | [代码](https://github.com/Haonan-Ge/selectstream) · [项目](https://haonan-ge.github.io/selectstream/) |
| 2026.05 | [**OmniMem**](https://arxiv.org/abs/2606.07577) | 按音频和视觉分别设置记忆预算，并压缩对应缓存。 | [代码分支](https://github.com/bytedance/SALMONN/tree/omni_mem) |
| 2026.04 | [**StreamMeCo**](https://arxiv.org/abs/2604.09000) | **智能体记忆：** 通过图剪枝与时间衰减检索保留有用事件。 | [代码](https://github.com/Celina-love-sweet/StreamMeCo) |
| 2026.04 | [**SimpleStream**](https://arxiv.org/abs/2604.02317) | 以近期帧滑动窗口为基线，检验历史记忆的价值。 | [代码](https://github.com/EvolvingLMMs-Lab/SimpleStream) |
| 2026.03 | [**FluxMem**](https://arxiv.org/abs/2603.02096) | 去除帧间冗余 token，并合并每帧内部的重复区域。 | [代码](https://github.com/ShareLab-SII/FluxMem) |
| 2026.02 | [**FreshMem**](https://arxiv.org/abs/2602.01683) | 结合频域摘要与分情景存储的空间缩略图，构建流式记忆。 | — |
| 2025.09 | [**StreamForest**](https://arxiv.org/abs/2509.24871) | 结合持久事件记忆与细致的短期视觉上下文。 | [代码](https://github.com/MCG-NJU/StreamForest) |
| 2025.08 | [**StreamMem**](https://arxiv.org/abs/2508.15717) | 在未知后续问题时，对视觉缓存条目进行剪枝与合并。 | [项目](https://yangyanl.ai/streammem/) |
| 2025.08 | [**M3-Agent**](https://arxiv.org/abs/2508.09736) | 构建以实体为中心的视听情景记忆和语义记忆，支持迭代推理。 | [代码](https://github.com/ByteDance-Seed/m3-agent) |
| 2025.01 | [**StreamChat · Xiong et al.**](https://arxiv.org/abs/2501.13468) | 通过层次化视觉记忆与并行调度，支持多轮流式对话。 | [代码](https://github.com/hmxiong/StreamChat) |

<details open>
<summary>相关文本智能体记忆</summary>

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2025.02 | [**A-MEM**](https://arxiv.org/abs/2502.12110) | 关联结构化文字笔记，并随经验积累更新记忆。 | [代码](https://github.com/WujiangXu/A-mem-sys) |
| 2023.10 | [**MemGPT**](https://arxiv.org/abs/2310.08560) | 在工作上下文与外部记忆间调配信息，支持持续交互的助手。 | [项目](https://research.memgpt.ai/) |

</details>

## 跨模态同步

**视觉观测、声音和语言如何在时间上对齐？**

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.09 | [**OmniTide**](https://arxiv.org/abs/2609.34653) | 协同设计流式视听处理、模态感知的信息保留与紧凑缓存。 | [运行时](https://github.com/tc-mb/llama.cpp-omni) |
| 2026.09 | [**Omni-Streaming Thinking**](https://arxiv.org/abs/2609.15128) | 核验暂定的视听判断，撤回被证据否定的记忆状态。 | [代码](https://github.com/EnjunDu/OST) · [项目](https://enjundu.com/blog/ost/) |
| 2026.09 | [**Realtime-Venus**](https://arxiv.org/abs/2609.13814) | 在全双工视听交互中，将后台任务异步交给智能体处理。 | [代码](https://github.com/inclusionAI/Realtime-Venus) |
| 2026.09 | [**Gander**](https://arxiv.org/abs/2609.08977) | 将持续视听交互与异步智能体循环结合。 | [代码](https://github.com/Omni-Interaction-Gander/Omni-Interaction-Agent) |
| 2026.08 | [**TLive-Omni**](https://arxiv.org/abs/2608.20958) | 对齐带时间戳的视听证据，以文字完成电商直播理解任务。 | [代码](https://github.com/TaoLiveAIGC/TLive-Omni) |
| 2026.08 | [**Aero Realtime**](https://arxiv.org/abs/2608.08469) | 在持续感知音视频输入的同时，生成与输入流对齐的文字回复。 | [代码](https://github.com/kcz358/aero-realtime) · [项目](https://kcz358.github.io/aero-realtime/) |
| 2026.06 | [**DuplexOmni**](https://arxiv.org/abs/2606.09186) | 将流式视听交互与独立的推理和工具调用层结合。 | — |
| 2026.04 | [**MiniCPM-o 4.5**](https://arxiv.org/abs/2604.27393) | 对齐持续视听输入与语音输出，支持全双工交互。 | [代码](https://github.com/OpenBMB/MiniCPM-V) |
| 2026.01 | [**ROMA**](https://arxiv.org/abs/2601.10323) | 同步音视频片段，并独立决定何时发言。 | [代码](https://github.com/Eureka-Maggie/ROMA) · [项目](https://eureka-maggie.github.io/ROMA_show/) |
| 2025.09 | [**Qwen3-Omni**](https://arxiv.org/abs/2509.17765) | 结合时间戳对齐、分块多模态输入与流式语音合成。 | [代码](https://github.com/QwenLM/Qwen3-Omni) |
| 2025.06 | [**Stream-Omni**](https://arxiv.org/abs/2506.13642) | 将视觉、语音与语言对齐，支持基于视觉的语音交互。 | [代码](https://github.com/ictnlp/Stream-Omni) |
| 2025.06 | [**RoboEgo**](https://arxiv.org/abs/2506.01934) | 持续处理视觉与语音上下文，同时生成同步回复。 | — |
| 2025.03 | [**Qwen2.5-Omni**](https://arxiv.org/abs/2503.20215) | 通过时间对齐的音视频片段进行理解，输出文字和语音。 | [代码](https://github.com/QwenLM/Qwen2.5-Omni) |

## 在线推理与交互

**当新证据到来时，系统何时应思考、回应或行动？**

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**OneStreamer**](https://arxiv.org/abs/2610.01762) | 联合学习事实描述记忆与主动回应，依据证据确定回应时机。 | [代码](https://github.com/MCG-NJU/OneStreamer) · [项目](https://mcg-nju.github.io/OneStreamer/) |
| 2026.06 | [**LyraV**](https://arxiv.org/abs/2606.06991) | 在每帧的实时处理时限内，交错处理新到帧与文字解码。 | — |
| 2026.03 | [**StreamingClaw**](https://arxiv.org/abs/2603.22120) | 将实时多模态感知、共享记忆、主动推理与工具调用结合。 | [项目](https://jackyu6.github.io/StreamingClaw-Page/) |
| 2026.03 | [**Em-Garde**](https://arxiv.org/abs/2603.19054) | 将查询解析为视觉线索，与持续到来的观测匹配并触发回应。 | [代码](https://github.com/air-embodied-brain/Em-Garde) |
| 2026.03 | [**ThinkStream**](https://arxiv.org/abs/2603.12938) | 借助压缩的推理记忆，交错进行观察、推理和发言决策。 | [代码](https://github.com/CASIA-IVA-Lab/ThinkStream) |
| 2026.03 | [**Think While Watching**](https://arxiv.org/abs/2603.11896) | 片段级记忆仅依赖已观测输入，支持视频感知与多轮推理重叠执行。 | [代码](https://github.com/wanglu-cs/Think_While_Watching) |
| 2026.03 | [**VST**](https://arxiv.org/abs/2603.12262) | 对新到片段进行推理，并积累思考以供后续回应。 | [代码](https://github.com/1ranGuan/VST) |
| 2026.03 | [**StreamReady**](https://arxiv.org/abs/2603.08620) | 判断回答问题所需的充分证据何时到达。 | [代码](https://github.com/sacrcv/StreamReady) · [项目](https://sacrcv.github.io/StreamReady-website/) |
| 2026.03 | [**Proact-VL**](https://arxiv.org/abs/2603.03447) | 持续处理游戏视频流，学习何时解说或提供指导。 | [项目](https://proact-vl.github.io/) |
| 2025.12 | [**MMDuet2**](https://arxiv.org/abs/2512.06810) | 通过多轮强化学习改进主动回应的时机与内容。 | [代码](https://github.com/yellow-binary-tree/MMDuet2) |
| 2025.08 | [**StreamAgent**](https://arxiv.org/abs/2508.01875) | 通过任务驱动的规划预判后续证据，并调整视觉注意力。 | — |
| 2025.05 | [**StreamBridge**](https://arxiv.org/abs/2505.05467) | 为离线视频模型加入压缩对话记忆与轻量触发机制。 | [代码](https://github.com/apple-aiml-research/ml-streambridge) |
| 2025.03 | [**ViSpeak**](https://arxiv.org/abs/2503.12769) | 在持续视频流中回应视觉指令与手势。 | [代码](https://github.com/HumanMLLM/ViSpeak) |
| 2025.01 | [**Dispider**](https://arxiv.org/abs/2501.03218) | 将视觉感知、回应决策与异步回答生成分离。 | [代码](https://github.com/Mark12Ding/Dispider) |
| 2024.12 | [**VideoChat-Online**](https://arxiv.org/abs/2501.00584) | 通过金字塔记忆与交错对话训练，支持在线视频对话。 | [代码](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024.11 | [**MMDuet**](https://arxiv.org/abs/2411.17991) | 通过增量视频与文字对话，学习回应时机与信息量。 | [代码](https://github.com/yellow-binary-tree/MMDuet) |

<details open>
<summary>相关语音与智能体交互</summary>

| 日期 | 论文 | 核心思路 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**Diffuplex**](https://arxiv.org/abs/2610.17780) | **语音：** 将轮次切换决策与基于扩散的并行回答生成分离。 | — |
| 2026.10 | [**RUBATO**](https://arxiv.org/abs/2610.14299) | **语音：** 将实时对话时钟与适配硬件的推理流分离。 | — |
| 2026.10 | [**DuplexAgent-RSI**](https://arxiv.org/abs/2610.11299) | **语音智能体：** 协调实时对话与异步推理、编程。 | [项目](https://amphionteam.github.io/DuplexAgent-RSI-Demo/) |
| 2024.09 | [**Moshi**](https://arxiv.org/abs/2410.00037) | **语音：** 建模用户与助手重叠的音频流，实现全双工对话。 | [代码](https://github.com/kyutai-labs/moshi) |

</details>

## 评测基准

**系统能否理解输入流、记住相关历史，并及时回应？**

| 日期 | 评测基准 | 评测内容 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**DIVE**](https://arxiv.org/abs/2610.28405) | 全双工视觉交互中的持续参与、回复修正、发言决策与回应时机。 | — |
| 2026.10 | [**FastBench**](https://arxiv.org/abs/2610.12427) | 高动态视频流中的快速事件与细粒度时间感知。 | [代码](https://github.com/Ashone3/FastBench) |
| 2026.06 | [**EgoSAT**](https://arxiv.org/abs/2606.24422) | 第一人称流式场景中的过去、当前与未来推理，以及可回答性和置信度诊断。 | [代码](https://github.com/leiyj23/EgoSAT) · [项目](https://leiyj23.github.io/EgoSAT/) |
| 2026.05 | [**IPIBench**](https://arxiv.org/abs/2605.27074) | 主动监测、变化的用户请求，以及响应式与主动式混合交互。 | [代码](https://github.com/lijinzhao30/IPI) · [项目](https://lijinzhao30.github.io/IPIBench/) |
| 2026.05 | [**SOVBench**](https://arxiv.org/abs/2605.25621) | 流式音视频多轮推理，以及基于证据的回应触发。 | — |
| 2026.05 | [**OmniPro**](https://arxiv.org/abs/2605.18577) | 联合评测视听理解与主动回应时机，并诊断对声音线索的依赖。 | [代码](https://github.com/RuixiangZhao/OmniPro) · [项目](https://ruixiangzhao.github.io/OmniPro/) |
| 2026.03 | [**RIVER**](https://arxiv.org/abs/2603.03985) | 对话中的历史回忆、实时感知与主动预判。 | [代码](https://github.com/OpenGVLab/RIVER) |
| 2026.03 | [**Live Gaming Benchmark**](https://arxiv.org/abs/2603.03447) | 持续观测下的游戏解说、协同解说与用户指导。 | [项目](https://proact-vl.github.io/) |
| 2025.07 | [**ProactiveVideoQA**](https://arxiv.org/abs/2507.09313) | 通过 PAUC 联合评估主动回答的质量与时机。 | [代码](https://github.com/yellow-binary-tree/ProactiveVideoQA) |
| 2025.07 | [**OST-Bench**](https://arxiv.org/abs/2507.07984) | 基于增量观测与历史上下文的在线空间推理。 | [项目](https://rbler1234.github.io/OSTBench.github.io/) |
| 2025.05 | [**RTV-Bench**](https://arxiv.org/abs/2505.02064) | 通过连续时间戳上的问题，评估持续感知与推理。 | [代码](https://github.com/LJungang/RTV-Bench) |
| 2025.03 | [**OmniMMI**](https://arxiv.org/abs/2503.22952) | 流式视听交互、基于观测的状态判断、行动规划与主动回应。 | [项目](https://omnimmi.github.io/) |
| 2025.02 | [**SVBench**](https://arxiv.org/abs/2502.10810) | 跨越长视频流、具有时序关联的多轮问题链。 | [代码](https://github.com/sotayang/SVBench) |
| 2025.01 | [**StreamBench**](https://arxiv.org/abs/2501.13468) | 需要短期和长期记忆的多轮流式对话。 | [代码](https://github.com/hmxiong/StreamChat) |
| 2025.01 | [**OVO-Bench**](https://arxiv.org/abs/2501.05510) | 历史追溯、当前感知，以及判断充分证据何时到达。 | [代码](https://github.com/JoeLeelyf/OVO-Bench) |
| 2024.12 | [**OVBench**](https://arxiv.org/abs/2501.00584) | 在线观测中的历史记忆、当前感知与未来预测。 | [代码](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024.11 | [**StreamingBench**](https://arxiv.org/abs/2411.03628) | 流式任务中带时间戳的视觉、视听与上下文理解。 | [代码](https://github.com/THUNLP-MT/StreamingBench) |

<details open>
<summary>辅助离线诊断与智能体时序评测</summary>

| 日期 | 评测基准 | 评测内容 | 资源 |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**Realtime-Bench**](https://arxiv.org/abs/2610.22155) | **智能体时序：** 不同时间机制下，在变化的网页和游戏环境中执行动作。 | [代码](https://github.com/RealtimeAgents/Realtime-Bench) · [项目](https://realtimeagents.org/) |
| 2026.01 | [**TimeBlind**](https://arxiv.org/abs/2602.00288) | **离线：** 通过配对视频，单独检验时间结构差异。 | [项目](https://baiqi-li.github.io/timeblind_project/) |
| 2025.05 | [**Daily-Omni**](https://arxiv.org/abs/2505.17862) | **离线：** 需要跨模态时间对齐的视听事件推理。 | [代码](https://github.com/Lliar-liar/Daily-Omni) |
| 2025.02 | [**WorldSense**](https://arxiv.org/abs/2502.04326) | **离线：** 语言与字幕条件下的同步视听理解。 | [项目](https://jaaackhongggg.github.io/WorldSense/) |
| 2024.10 | [**TemporalBench**](https://arxiv.org/abs/2410.10818) | **离线：** 事件顺序、动作频率与细粒度时间差异。 | [项目](https://temporalbench.github.io/) |
| 2024.09 | [**OmniBench**](https://arxiv.org/abs/2409.15272) | **离线：** 利用互补的图像、音频和文字证据进行推理。 | [代码](https://github.com/multimodal-art-projection/OmniBench) |

</details>

---

[参与贡献](CONTRIBUTING.md) · 联系方式：[yuanqing.wang@utdallas.edu](mailto:yuanqing.wang@utdallas.edu)

<details open>
<summary>引用本仓库</summary>

如果本仓库对你有帮助，欢迎引用：

```bibtex
@misc{wang2026streamingmultimodal,
  author       = {Wang, Yuanqing},
  title        = {{Awesome Streaming Multimodal Understanding and Interaction}},
  year         = {2026},
  howpublished = {GitHub repository},
  url          = {https://github.com/Wang-Yuanqing/Awesome-Streaming-Multimodal-Understanding-and-Interaction}
}
```

</details>
