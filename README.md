<div align="center">

# Awesome Streaming Multimodal<br>Understanding and Interaction

**Continuous perception. Useful memory. Timely interaction.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Papers](https://img.shields.io/badge/papers-77-blue)
![Updated](https://img.shields.io/badge/updated-2026--10--21-green)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange)](CONTRIBUTING.md)

</div>

Our goal is AI that follows the world as it unfolds: understanding **text, images, video, and audio**, remembering what matters, and responding through **text and speech**. We focus on systems that update their understanding as observations arrive, using only evidence available so far and keeping memory and response delay manageable.

[Temporal understanding](#temporal-understanding) · [Memory](#memory) · [Cross-modal synchronization](#cross-modal-synchronization) · [Online reasoning and interaction](#online-reasoning-and-interaction) · [Benchmarks](#benchmarks)

Dates show the first preprint month; entries are newest first within each table.

## Temporal Understanding

**What happened, in what order, and what changed?**

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2026.08 | [**StreamOPD**](https://arxiv.org/abs/2608.16320) | Distills causal responses using privileged spatiotemporal cues during training. | [Code](https://github.com/UniX-AI-Lab/StreamOPD) · [Project](https://unix-ai-lab.github.io/StreamOPD/) |
| 2026.03 | [**ColorTrigger**](https://arxiv.org/abs/2603.22466) | Preserves continuous grayscale observations while requesting color when informative. | [Project](https://lvgd.github.io/ColorTrigger/) |
| 2026.03 | [**OmniStream**](https://arxiv.org/abs/2603.12265) | Causal visual backbone learns temporal, spatial, and language-aligned representations. | [Code](https://github.com/Go2Heart/OmniStream) |
| 2025.09 | [**OpenHOUSE**](https://arxiv.org/abs/2509.12145) | Detects action boundaries and describes events at multiple temporal scales. | — |
| 2025.04 | [**TimeChat-Online**](https://arxiv.org/abs/2504.17343) | Drops redundant visual tokens while retaining changes across incoming frames. | [Code](https://github.com/yaolinli/TimeChat-Online) · [Project](https://timechat-online.github.io/) |
| 2025.04 | [**LiveCC**](https://arxiv.org/abs/2504.16030) | Learns temporal alignment from timestamped transcripts for live video commentary. | [Code](https://github.com/showlab/livecc) · [Project](https://showlab.github.io/livecc/) |
| 2024.06 | [**VideoLLM-online**](https://arxiv.org/abs/2406.11816) | Learns streaming dialogue and when to respond within arriving video. | [Code](https://github.com/showlab/videollm-online) |

## Memory

**What should the system keep, update, and retrieve as the stream grows?**

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**MaLoW**](https://arxiv.org/abs/2610.22070) | Stores long-term streaming history in fixed-size, evolving LoRA weights. | [Code](https://github.com/dragonlzm/MaLoW) · [Project](https://dragonlzm.github.io/MaLoW/) |
| 2026.10 | [**DeltaStreamer**](https://arxiv.org/abs/2610.19849) | Records visual changes as text; retrieves memories and replays evidence. | [Code](https://github.com/BBBBchan/DeltaStreamer) · [Project](https://bbbbchan.github.io/DeltaStreamer/) |
| 2026.10 | [**FlashBack**](https://arxiv.org/abs/2610.01192) | Gates historical recall through separate cache pathways, preserving current perception. | — |
| 2026.09 | [**MEMO**](https://arxiv.org/abs/2609.38900) | Entity-aware indices retrieve separately archived high-resolution visual evidence on demand. | [Code](https://github.com/Cecilia384/MEMO) |
| 2026.09 | [**EGSD**](https://arxiv.org/abs/2609.36803) | Event-grounded self-distillation preserves entity coverage in incremental memory. | — |
| 2026.09 | [**MemEvo**](https://arxiv.org/abs/2609.36581) | Uses program search to discover causal memory mechanisms under budgets. | — |
| 2026.09 | [**SVMemAgent**](https://arxiv.org/abs/2609.18540) | Learns to select and replace memory frames before queries arrive. | — |
| 2026.09 | [**MemForest**](https://arxiv.org/abs/2609.08273) | **Agent memory:** event trees compress memories and guide temporal retrieval. | [Code](https://github.com/Celina-love-sweet/MemForest) |
| 2026.09 | [**CoFiE**](https://arxiv.org/abs/2609.03675) | Filters novel frames before encoding, then selects finer query evidence. | — |
| 2026.09 | [**ShallowStream**](https://arxiv.org/abs/2609.02780) | Builds shallow cache indices for selective historical evidence retrieval. | [Code](https://github.com/CURRENTF/ShallowStream) |
| 2026.08 | [**StreamScout**](https://arxiv.org/abs/2609.00291) | Adapts memory access from textual timelines to detailed visual evidence. | — |
| 2026.08 | [**StreamEMS**](https://arxiv.org/abs/2608.27881) | Restructures visual memories through semantic and prior-informed memory evolution. | — |
| 2026.08 | [**StreamFlow**](https://arxiv.org/abs/2608.10949) | Filters redundant observations and retrieves visual latents during response generation. | — |
| 2026.07 | [**FOLIO**](https://arxiv.org/abs/2607.13298) | Maintains entity-focused semantic memory linked to original visual evidence. | — |
| 2026.06 | [**SelectStream**](https://arxiv.org/abs/2606.16353) | Combines surprise-driven writing with graph retrieval in fixed-capacity latent memory. | [Code](https://github.com/Haonan-Ge/selectstream) · [Project](https://haonan-ge.github.io/selectstream/) |
| 2026.05 | [**OmniMem**](https://arxiv.org/abs/2606.07577) | Compresses audio and visual caches with separate, modality-aware memory budgets. | [Code branch](https://github.com/bytedance/SALMONN/tree/omni_mem) |
| 2026.04 | [**StreamMeCo**](https://arxiv.org/abs/2604.09000) | **Agent memory:** graph pruning and time-decay retrieval retain useful events. | [Code](https://github.com/Celina-love-sweet/StreamMeCo) |
| 2026.04 | [**SimpleStream**](https://arxiv.org/abs/2604.02317) | Recent-frame sliding-window baseline for testing the value of historical memory. | [Code](https://github.com/EvolvingLMMs-Lab/SimpleStream) |
| 2026.03 | [**FluxMem**](https://arxiv.org/abs/2603.02096) | Removes redundant inter-frame tokens and merges repetitive regions within each frame. | [Code](https://github.com/ShareLab-SII/FluxMem) |
| 2026.02 | [**FreshMem**](https://arxiv.org/abs/2602.01683) | Combines frequency-domain summaries with episodic spatial thumbnails for streaming memory. | — |
| 2025.09 | [**StreamForest**](https://arxiv.org/abs/2509.24871) | Combines persistent event memory with detailed short-term visual context. | [Code](https://github.com/MCG-NJU/StreamForest) |
| 2025.08 | [**StreamMem**](https://arxiv.org/abs/2508.15717) | Prunes and merges visual cache entries before future questions are known. | [Project](https://yangyanl.ai/streammem/) |
| 2025.08 | [**M3-Agent**](https://arxiv.org/abs/2508.09736) | Builds entity-centric audiovisual episodic and semantic memory for iterative reasoning. | [Code](https://github.com/ByteDance-Seed/m3-agent) |
| 2025.01 | [**StreamChat · Xiong et al.**](https://arxiv.org/abs/2501.13468) | Hierarchical visual memory and parallel scheduling support multi-turn streaming dialogue. | [Code](https://github.com/hmxiong/StreamChat) |

<details>
<summary>Related text-agent memory</summary>

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2025.02 | [**A-MEM**](https://arxiv.org/abs/2502.12110) | Links structured text notes and updates memories as experiences accumulate. | [Code](https://github.com/WujiangXu/A-mem-sys) |
| 2023.10 | [**MemGPT**](https://arxiv.org/abs/2310.08560) | Moves information between working context and external memory for persistent assistants. | [Project](https://research.memgpt.ai/) |

</details>

## Cross-modal Synchronization

**How do visual observations, sounds, and language line up in time?**

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2026.09 | [**OmniTide**](https://arxiv.org/abs/2609.34653) | Co-designs audiovisual streaming with modality-aware retention and compact cache storage. | [Runtime](https://github.com/tc-mb/llama.cpp-omni) |
| 2026.09 | [**Omni-Streaming Thinking**](https://arxiv.org/abs/2609.15128) | Verifies provisional audiovisual claims and retracts contradicted memory states. | [Code](https://github.com/EnjunDu/OST) · [Project](https://enjundu.com/blog/ost/) |
| 2026.09 | [**Realtime-Venus**](https://arxiv.org/abs/2609.13814) | Full-duplex audiovisual interaction delegates background tasks asynchronously to agents. | [Code](https://github.com/inclusionAI/Realtime-Venus) |
| 2026.09 | [**Gander**](https://arxiv.org/abs/2609.08977) | Connects continuous audiovisual interaction with an asynchronous agent loop. | [Code](https://github.com/Omni-Interaction-Gander/Omni-Interaction-Agent) |
| 2026.08 | [**TLive-Omni**](https://arxiv.org/abs/2608.20958) | Aligns timestamped audiovisual evidence for text-based live-commerce understanding. | [Code](https://github.com/TaoLiveAIGC/TLive-Omni) |
| 2026.06 | [**DuplexOmni**](https://arxiv.org/abs/2606.09186) | Streams audiovisual interaction alongside a separate reasoning and tool-use layer. | — |
| 2026.04 | [**MiniCPM-o 4.5**](https://arxiv.org/abs/2604.27393) | Aligns continuous audiovisual input and speech output for full-duplex interaction. | [Code](https://github.com/OpenBMB/MiniCPM-V) |
| 2026.01 | [**ROMA**](https://arxiv.org/abs/2601.10323) | Synchronizes audio and video chunks with separate decisions about speaking. | [Code](https://github.com/Eureka-Maggie/ROMA) · [Project](https://eureka-maggie.github.io/ROMA_show/) |
| 2025.09 | [**Qwen3-Omni**](https://arxiv.org/abs/2509.17765) | Combines timestamp alignment, chunked multimodal input, and streaming speech synthesis. | [Code](https://github.com/QwenLM/Qwen3-Omni) |
| 2025.06 | [**Stream-Omni**](https://arxiv.org/abs/2506.13642) | Aligns vision and speech with language for vision-grounded spoken interaction. | [Code](https://github.com/ictnlp/Stream-Omni) |
| 2025.03 | [**Qwen2.5-Omni**](https://arxiv.org/abs/2503.20215) | Time-aligned audiovisual chunks support understanding with text and speech responses. | [Code](https://github.com/QwenLM/Qwen2.5-Omni) |

## Online Reasoning and Interaction

**When should the system think, respond, or act as new evidence arrives?**

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**OneStreamer**](https://arxiv.org/abs/2610.01762) | Jointly learns factual caption memory and evidence-timed proactive responses. | [Code](https://github.com/MCG-NJU/OneStreamer) · [Project](https://mcg-nju.github.io/OneStreamer/) |
| 2026.06 | [**LyraV**](https://arxiv.org/abs/2606.06991) | Interleaves arriving frames and text decoding within real-time frame budgets. | — |
| 2026.03 | [**ThinkStream**](https://arxiv.org/abs/2603.12938) | Interleaves watching, reasoning, and speaking decisions with compressed reasoning memory. | [Code](https://github.com/CASIA-IVA-Lab/ThinkStream) |
| 2026.03 | [**Think While Watching**](https://arxiv.org/abs/2603.11896) | Segment-level causal memory overlaps video perception and multi-turn reasoning. | [Code](https://github.com/wanglu-cs/Think_While_Watching) |
| 2026.03 | [**VST**](https://arxiv.org/abs/2603.12262) | Reasons over incoming clips and accumulates thoughts for later responses. | [Code](https://github.com/1ranGuan/VST) |
| 2026.03 | [**StreamReady**](https://arxiv.org/abs/2603.08620) | Predicts when sufficient evidence has arrived to answer a question. | [Code](https://github.com/sacrcv/StreamReady) · [Project](https://sacrcv.github.io/StreamReady-website/) |
| 2025.12 | [**MMDuet2**](https://arxiv.org/abs/2512.06810) | Uses multi-turn reinforcement learning to improve proactive timing and responses. | [Code](https://github.com/yellow-binary-tree/MMDuet2) |
| 2025.08 | [**StreamAgent**](https://arxiv.org/abs/2508.01875) | Anticipates future evidence and adjusts visual attention through task-driven planning. | — |
| 2025.05 | [**StreamBridge**](https://arxiv.org/abs/2505.05467) | Adds compressed dialogue memory and lightweight triggers to offline video models. | [Code](https://github.com/apple-aiml-research/ml-streambridge) |
| 2025.03 | [**ViSpeak**](https://arxiv.org/abs/2503.12769) | Responds to visual instructions and gestures within ongoing video streams. | [Code](https://github.com/HumanMLLM/ViSpeak) |
| 2025.01 | [**Dispider**](https://arxiv.org/abs/2501.03218) | Separates visual perception, response decisions, and asynchronous response generation. | [Code](https://github.com/Mark12Ding/Dispider) |
| 2024.12 | [**VideoChat-Online**](https://arxiv.org/abs/2501.00584) | Pyramid memory and interleaved dialogue training support online video conversations. | [Code](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024.11 | [**MMDuet**](https://arxiv.org/abs/2411.17991) | Learns response timing and informativeness through incremental video-text dialogue. | [Code](https://github.com/yellow-binary-tree/MMDuet) |

<details>
<summary>Related speech and agent interaction</summary>

| Date | Paper | Core idea | Resources |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**Diffuplex**](https://arxiv.org/abs/2610.17780) | **Speech:** separates turn-taking decisions from parallel diffusion-based response generation. | — |
| 2026.10 | [**RUBATO**](https://arxiv.org/abs/2610.14299) | **Speech:** separates real-time dialogue clocks from hardware-adaptive reasoning streams. | — |
| 2026.10 | [**DuplexAgent-RSI**](https://arxiv.org/abs/2610.11299) | **Speech agent:** coordinates live conversation with asynchronous reasoning and coding. | [Project](https://amphionteam.github.io/DuplexAgent-RSI-Demo/) |
| 2024.09 | [**Moshi**](https://arxiv.org/abs/2410.00037) | **Speech:** models overlapping user and assistant audio for full-duplex dialogue. | [Code](https://github.com/kyutai-labs/moshi) |

</details>

## Benchmarks

**Can the system understand the stream, remember relevant history, and respond on time?**

| Date | Benchmark | What it tests | Resources |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**FastBench**](https://arxiv.org/abs/2610.12427) | Fast events and fine temporal perception in high-dynamic video streams. | [Code](https://github.com/Ashone3/FastBench) |
| 2026.05 | [**IPIBench**](https://arxiv.org/abs/2605.27074) | Proactive monitoring, changing user requests, and mixed reactive-proactive interaction. | [Code](https://github.com/lijinzhao30/IPI) · [Project](https://lijinzhao30.github.io/IPIBench/) |
| 2026.03 | [**RIVER**](https://arxiv.org/abs/2603.03985) | Retrospective memory, live perception, and proactive anticipation in dialogue. | [Code](https://github.com/OpenGVLab/RIVER) |
| 2025.07 | [**ProactiveVideoQA**](https://arxiv.org/abs/2507.09313) | Proactive answer quality and timing, evaluated jointly with PAUC. | [Code](https://github.com/yellow-binary-tree/ProactiveVideoQA) |
| 2025.07 | [**OST-Bench**](https://arxiv.org/abs/2507.07984) | Online spatial reasoning over incrementally acquired observations and historical context. | [Project](https://rbler1234.github.io/OSTBench.github.io/) |
| 2025.05 | [**RTV-Bench**](https://arxiv.org/abs/2505.02064) | Continuous perception and reasoning through questions at successive timestamps. | [Code](https://github.com/LJungang/RTV-Bench) |
| 2025.03 | [**OmniMMI**](https://arxiv.org/abs/2503.22952) | Audiovisual streaming interaction, state grounding, action planning, and proactive responses. | [Project](https://omnimmi.github.io/) |
| 2025.02 | [**SVBench**](https://arxiv.org/abs/2502.10810) | Temporal multi-turn question chains spanning long video streams. | [Code](https://github.com/sotayang/SVBench) |
| 2025.01 | [**StreamBench**](https://arxiv.org/abs/2501.13468) | Multi-turn streaming dialogue with short-term and long-term memory demands. | [Code](https://github.com/hmxiong/StreamChat) |
| 2025.01 | [**OVO-Bench**](https://arxiv.org/abs/2501.05510) | Historical tracing, current perception, and deciding when enough evidence arrives. | [Code](https://github.com/JoeLeelyf/OVO-Bench) |
| 2024.12 | [**OVBench**](https://arxiv.org/abs/2501.00584) | Past memory, present perception, and future prediction during online viewing. | [Code](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024.11 | [**StreamingBench**](https://arxiv.org/abs/2411.03628) | Timestamped visual, audiovisual, and contextual understanding across streaming tasks. | [Code](https://github.com/THUNLP-MT/StreamingBench) |

<details>
<summary>Supporting offline diagnostics and agent timing</summary>

| Date | Benchmark | What it tests | Resources |
| :--- | :--- | :--- | :--- |
| 2026.10 | [**Realtime-Bench**](https://arxiv.org/abs/2610.22155) | **Agent timing:** actions in changing web/game environments under different clocks. | [Code](https://github.com/RealtimeAgents/Realtime-Bench) · [Project](https://realtimeagents.org/) |
| 2026.01 | [**TimeBlind**](https://arxiv.org/abs/2602.00288) | **Offline:** matched video pairs isolate differences in temporal structure. | [Project](https://baiqi-li.github.io/timeblind_project/) |
| 2025.05 | [**Daily-Omni**](https://arxiv.org/abs/2505.17862) | **Offline:** audiovisual event reasoning requiring temporal alignment across modalities. | [Code](https://github.com/Lliar-liar/Daily-Omni) |
| 2025.02 | [**WorldSense**](https://arxiv.org/abs/2502.04326) | **Offline:** synchronized audiovisual understanding with language and subtitle conditions. | [Project](https://jaaackhongggg.github.io/WorldSense/) |
| 2024.10 | [**TemporalBench**](https://arxiv.org/abs/2410.10818) | **Offline:** event order, action frequency, and fine temporal distinctions. | [Project](https://temporalbench.github.io/) |
| 2024.09 | [**OmniBench**](https://arxiv.org/abs/2409.15272) | **Offline:** reasoning from complementary image, audio, and text evidence. | [Code](https://github.com/multimodal-art-projection/OmniBench) |

</details>

---

[Contribute](CONTRIBUTING.md) · Contact: [yuanqing.wang@utdallas.edu](mailto:yuanqing.wang@utdallas.edu)

<details>
<summary>Cite this repository</summary>

If you find this repository helpful, please consider citing it:

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
