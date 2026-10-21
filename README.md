# Awesome Streaming Multimodal Understanding and Interaction

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![GitHub last commit](https://img.shields.io/github/last-commit/Wang-Yuanqing/Awesome-Streaming-Multimodal-Understanding-and-Interaction)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> Continuously understand text, images, video, and audio; maintain relevant memory; and interact through text and speech as events unfold.

The world unfolds over time. An assistant helping someone cook, follow a lecture, or complete a task needs to connect what it sees, hears, reads, and remembers while new events are still happening.

This repository collects research toward **streaming multimodal understanding and interaction**: models, training methods, memory systems, agent architectures, datasets, and evaluations. The central questions are **temporal understanding, memory, cross-modal synchronization, and online reasoning and interaction**.

**Inputs:** text, images, video, and audio, including speech and environmental sounds. **Responses:** text and speech. Image and video generation are outside the primary scope.

**Literature reviewed:** 2026-10-21. This is a selected reading list, not an exhaustive survey or a performance leaderboard.

## Contents

- [Scope and streaming criteria](#scope-and-streaming-criteria)
- [Four core questions](#four-core-questions)
- [Temporal understanding](#temporal-understanding)
- [Memory](#memory)
- [Cross-modal synchronization](#cross-modal-synchronization)
- [Online reasoning and interaction](#online-reasoning-and-interaction)
- [Benchmarks and datasets](#benchmarks-and-datasets)
- [Reading results critically](#reading-results-critically)
- [Where to start](#where-to-start)
- [Contributing](#contributing)
- [Related resources](#related-resources)
- [Citation](#citation)
- [Contact](#contact)
- [License](#license)

## Scope and streaming criteria

We study systems that update their understanding as observations arrive. Text and images may arrive intermittently alongside continuous audio and video. Individual papers can address a subset of these inputs or one component of the system; every entry explains its relevance and boundaries.

Our target has five properties:

1. **Causal access:** use only observations available at the time of a response, including the available audio, transcript, and subtitle prefixes.
2. **Incremental processing:** incorporate new observations while the stream continues, with an explicit strategy for reusing computation.
3. **Persistent context:** maintain relevant events, entities, states, and unresolved questions across observations.
4. **Timely interaction:** respond, wait, or revise an answer when appropriate; distinguish answering a question from initiating a response or handling an interruption.
5. **Sustained operation:** characterize throughput, response delay, active memory, and any growing external storage over long streams.

Frames and short chunks can be useful computational units. What matters is how the system preserves temporal relationships, updates state, and interacts as new evidence arrives. Fixed-frame offline QA, a live-camera demo, or streaming speech synthesis alone does not demonstrate all five properties.

**Streaming input, streaming output, and full-duplex interaction are separate capabilities.** Full duplex here means continuing to perceive incoming information while producing a response. Inclusion in this list does not certify that a work satisfies every target property.

We also include supporting offline diagnostics and transferable agent components. These are labeled explicitly. Memory representations and system architecture remain open: text notes, structured records, visual/audio features, KV caches, evidence archives, and combinations of these are all relevant.

**Table conventions:** dates are first arXiv submission dates, which can differ from model releases and the month in an arXiv identifier. **T** = text, **I** = image, **V** = video, **A** = audio, **S** = speech output, a subset of audio. Capabilities refer to the linked work; a repository may contain newer releases. A project link does not imply released code or weights.

## Four core questions

| Question | What we want to understand | Evidence to look for |
|:--|:--|:--|
| [Temporal understanding](#temporal-understanding) | How do actions, event order, object identities, and states evolve? | Tasks requiring motion, brief events, ordering, or state transitions; controls for static-scene shortcuts. |
| [Memory](#memory) | What should be retained, updated, retrieved, or forgotten? | Delayed questions, long-range dependencies, memory budgets, and a clear account of access to original evidence. |
| [Cross-modal synchronization](#cross-modal-synchronization) | How do visual events, speech, environmental sounds, and text relate in time? | Tasks requiring complementary modalities and correct timing, including asynchronous arrivals and missing inputs. |
| [Online reasoning and interaction](#online-reasoning-and-interaction) | How should an assistant reason, respond, wait, and revise while observations continue? | Causal multi-turn interaction, response timing, interruptions, proactive behavior, and sustained runtime measurements. |

Works often span several questions. Each is placed near its main contribution rather than duplicated across every section.

## Temporal understanding

Temporal evidence includes what changed, what happened first, how often an action occurred, and which earlier event explains the current state. Training and evaluation should make this evidence necessary for the answer.

| Date | Work | Contribution and scope | Resources |
|:--|:--|:--|:--|
| 2025-04-22 | [**LiveCC: Learning Video LLM with Streaming Speech Transcription at Scale**](https://arxiv.org/abs/2504.16030) | Interleaves video frames and timestamped ASR words for temporally aligned training and live commentary. Transcript-based supervision does not itself establish raw-audio understanding. Includes Live-CC-5M, Live-WhisperX, and LiveSports-3K resources. | [Project](https://showlab.github.io/livecc/) · [Code](https://github.com/showlab/livecc) |
| 2024-06-17 | [**VideoLLM-online: Online Video Large Language Model for Streaming Video**](https://arxiv.org/abs/2406.11816) | LIVE training and streaming EOS prediction support temporally aligned dialogue and incremental cached inference over arriving video. The reported video/text pipeline does not establish synchronized audio input. | [Project](https://showlab.github.io/videollm-online/) · [Code](https://github.com/showlab/videollm-online) |

**Supporting diagnostics:** [TemporalBench](https://arxiv.org/abs/2410.10818) and [TimeBlind](https://arxiv.org/abs/2602.00288) test temporal distinctions. Their clip-based results alone do not establish streaming operation; see [benchmarks and datasets](#benchmarks-and-datasets).

## Memory

For open-ended streaming interaction, memory should retain useful evidence before future questions are known. Important choices include granularity, representation, update rules, retrieval, and whether omitted details can be recovered from stored observations.

### Streaming memory methods and baselines

| Date | Work | Contribution and scope | Resources |
|:--|:--|:--|:--|
| 2026-10-14 | [**DeltaStreamer: Towards Human-Like Agentic Streaming Video Understanding**](https://arxiv.org/abs/2610.19849) | Records visual changes in structured text memory, then plans retrieval and targeted replay when queried. Visual/text agent framework; answers can depend on archived historical frames, whose storage and access must be accounted for. | [Project](https://bbbbchan.github.io/DeltaStreamer/) · [Code](https://github.com/BBBBchan/DeltaStreamer) |
| 2026-05-26 | [**OmniMem: Perturbation-aware Memory Compression for Streaming Audio-Visual LLMs**](https://arxiv.org/abs/2606.07577) | Allocates separate audio/visual memory budgets and selects informative KV states. Directly relevant to audiovisual streaming compression; long-video QA evaluations do not demonstrate full-duplex live interaction. | [Author-linked repository branch](https://github.com/bytedance/SALMONN/tree/omni_mem) |
| 2026-04-02 | [**A Simple Baseline for Streaming Video Understanding (SimpleStream)**](https://arxiv.org/abs/2604.02317) | Feeds a VLM only a sliding window of recent frames. A baseline for separating current perception from long-range recall and testing the value of additional memory under matched protocols. | [Project](https://simple-stream.github.io/) · [Code](https://github.com/EvolvingLMMs-Lab/SimpleStream) |
| 2025-09-29 | [**StreamForest: Efficient Online Video Understanding with Persistent Event Memory**](https://arxiv.org/abs/2509.24871) | Combines hierarchical event memory with a detailed short-term spatiotemporal window. Visual memory and video QA; synchronized audio input and speech interaction are not established by this entry. | [Project](https://happyzqy.github.io/StreamForest/) · [Code](https://github.com/MCG-NJU/StreamForest) |
| 2025-08-21 | [**StreamMem: Query-Agnostic KV Cache Memory for Streaming Video Understanding**](https://arxiv.org/abs/2508.15717) | Filters incoming frames and prunes or merges visual KV entries into a fixed-size cache before user queries are known. Relevant to bounded visual memory. | [Project](https://yangyanl.ai/streammem/) |
| 2025-01-23 | [**Streaming Video Understanding and Multi-round Interaction with Memory-enhanced Knowledge**](https://arxiv.org/abs/2501.13468) | Xiong et al.'s StreamChat combines hierarchical video-feature memory and parallel scheduling for multi-turn dialogue. Introduces StreamBench; this entry concerns video/text interaction. | [Code and data](https://github.com/hmxiong/StreamChat) |

### Transferable agent memory and tool use

Text and coding agents offer useful designs for persistent context, retrieval, planning, and tool execution. A streaming assistant could write timestamped event notes, track task state, retrieve relevant evidence, and call tools while observation continues. These are system-design possibilities; the papers below do not establish streaming audiovisual capabilities.

| Date | Work | Transferable idea and demonstrated boundary | Resources |
|:--|:--|:--|:--|
| 2025-02-17 | [**A-MEM: Agentic Memory for LLM Agents**](https://arxiv.org/abs/2502.12110) | Builds linked structured notes and updates memory as new experiences arrive. A text-agent memory approach to investigate for multimodal event records. | [System code](https://github.com/WujiangXu/A-mem-sys) · [Evaluation code](https://github.com/WujiangXu/A-mem) |
| 2023-10-12 | [**MemGPT: Towards LLMs as Operating Systems**](https://arxiv.org/abs/2310.08560) | Model-controlled movement between memory tiers manages limited working context. Original evaluations concern documents and multi-session text conversations; the project has evolved into Letta. | [Research project](https://research.memgpt.ai/) · [Letta repository](https://github.com/letta-ai/letta) |
| 2023-04-07 | [**Generative Agents: Interactive Simulacra of Human Behavior**](https://arxiv.org/abs/2304.03442) | Natural-language observations, relevance/recency/importance retrieval, and reflection support planning in a simulated environment with textual observations. | [Code](https://github.com/joonspk-research/generative_agents) |

Text summaries can preserve useful semantics while discarding visual or acoustic detail. Hybrid memory can pair notes and entity states with embeddings and timestamped pointers to source evidence. Evaluate the cost and benefit of each representation, including any replay or external storage.

## Cross-modal synchronization

The system should connect evidence across modalities on a shared timeline. Speech transcripts capture words; environmental sounds, speaker cues, and visual events can contribute additional information. Supporting all four input types and aligning concurrent streams are distinct claims.

### Multimodal foundations

| Date | Work | Inputs → outputs | Streaming mechanism and boundary | Resources |
|:--|:--|:--|:--|:--|
| 2026-04-30 | [**MiniCPM-o 4.5: Towards Real-Time Full-Duplex Omni-Modal Interaction**](https://arxiv.org/abs/2604.27393) | T, I, V, A → T, S | Omni-Flow aligns inputs and outputs on a shared timeline, supporting concurrent audiovisual perception, response generation, and proactive behavior. | [Code](https://github.com/OpenBMB/MiniCPM-V) · [Model documentation](https://github.com/OpenBMB/MiniCPM-V/blob/main/docs/minicpm_o4dot5_en.md) |
| 2025-09-22 | [**Qwen3-Omni Technical Report**](https://arxiv.org/abs/2509.17765) | T, I, V, A → T, S | Absolute-time audiovisual alignment, chunked multimodal prefilling, and causal streaming speech synthesis. The report does not establish full-duplex listening/speaking control. | [Code](https://github.com/QwenLM/Qwen3-Omni) |
| 2025-03-26 | [**Qwen2.5-Omni Technical Report**](https://arxiv.org/abs/2503.20215) | T, I, V, A → T, S | Block-wise encoders, time-aligned audiovisual chunks, and streaming speech decoding. A foundation for streaming pipelines; full-duplex interaction requires separate evidence. | [Code](https://github.com/QwenLM/Qwen2.5-Omni) |

### Transferable speech interaction

| Date | Work | Contribution and scope | Resources |
|:--|:--|:--|:--|
| 2024-09-17 | [**Moshi: a speech-text foundation model for real-time dialogue**](https://arxiv.org/abs/2410.00037) | Models user and assistant audio streams for overlapping, full-duplex speech dialogue, with text aligned to generated speech. A speech interaction component with no visual input. | [Code](https://github.com/kyutai-labs/moshi) |

**Supporting diagnostics:** [Daily-Omni](https://arxiv.org/abs/2505.17862), [WorldSense](https://arxiv.org/abs/2502.04326), and [OmniBench](https://arxiv.org/abs/2409.15272) probe complementary multimodal evidence. Their offline protocols are listed separately below.

## Online reasoning and interaction

An assistant needs to decide what to say and when to say it, retain the context of an ongoing conversation, and incorporate new evidence. Reactive QA, proactive responses, and simultaneous perception and generation require different evaluations.

| Date | Work | Contribution and scope | Resources |
|:--|:--|:--|:--|
| 2026-03-12 | [**Video Streaming Thinking: VideoLLMs Can Watch and Think Simultaneously**](https://arxiv.org/abs/2603.12262) | VST performs causal reasoning over incoming clips and accumulates textual thoughts for later answers. Streaming SFT and RL address multi-turn video/text interaction; raw-audio input is not established. | [Project](https://1ranguan.github.io/VST/) · [Code](https://github.com/1ranGuan/VST) |
| 2025-01-06 | [**Dispider: Enabling Video LLMs with Active Real-Time Interaction via Disentangled Perception, Decision, and Reaction**](https://arxiv.org/abs/2501.03218) | Separates ongoing visual perception, response decisions, and asynchronous response generation to support proactive video/text interaction. | [Code](https://github.com/Mark12Ding/Dispider) |
| 2024-12-31 | [**Online Video Understanding: OVBench and VideoChat-Online**](https://arxiv.org/abs/2501.00584) | Combines a Pyramid Memory Bank with interleaved online dialogue training. Visual/video QA; distinguish its streaming evaluation setting from sliding-window evaluation. | [Project](https://videochat-online.github.io/) · [Code](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024-11-27 | [**VideoLLM Knows When to Speak: Enhancing Time-Sensitive Video Comprehension with Video-Text Duet Interaction Format**](https://arxiv.org/abs/2411.17991) | MMDuet learns response timing and informativeness through incremental video/text interaction. Its duet format alternates video reception and responses; it does not establish simultaneous full-duplex perception and decoding. | [Code, data, and demo](https://github.com/yellow-binary-tree/MMDuet) |

## Benchmarks and datasets

### Online and streaming evaluation

These benchmarks use timestamped questions or multi-turn streaming scenarios over recorded videos. A benchmark score must be read together with the implementation's causal access, state management, and runtime protocol.

| Date | Benchmark | Main focus | Protocol boundary | Resources |
|:--|:--|:--|:--|:--|
| 2025-01-23 | [**StreamBench (Xiong et al.)**](https://arxiv.org/abs/2501.13468) | Multi-round video interaction, short- and long-term memory, and contextual reasoning. | Video/text streaming interaction benchmark introduced with the StreamChat entry above. | [Code and data](https://github.com/hmxiong/StreamChat) |
| 2025-01-09 | [**OVO-Bench**](https://arxiv.org/abs/2501.05510) | Backward tracing, real-time visual perception, and forward active responding. | Timestamped video tasks; forward responding tests waiting for sufficient evidence as the stream advances. | [Code and benchmark](https://github.com/JoeLeelyf/OVO-Bench) |
| 2024-12-31 | [**OVBench**](https://arxiv.org/abs/2501.00584) | Past memory, current perception, and future prediction across online video tasks. | Report whether the implementation uses streaming or sliding-window evaluation. | [Project](https://videochat-online.github.io/) · [Code](https://github.com/MCG-NJU/VideoChat-Online) |
| 2024-11-06 | [**StreamingBench**](https://arxiv.org/abs/2411.03628) | Real-time visual, audiovisual omni-source, and contextual understanding. | Timestamped QA simulates streaming access; separately measure persistent state, throughput, and response timing. | [Project](https://streamingbench.github.io/) · [Code and benchmark](https://github.com/THUNLP-MT/StreamingBench) |

### Supporting offline diagnostics

These resources help isolate temporal or cross-modal reasoning. They are not evidence of causal online operation or timely interaction by themselves.

| Date | Benchmark | Main focus | Protocol | Resources |
|:--|:--|:--|:--|:--|
| 2026-01-30 | [**TimeBlind: A Spatio-Temporal Compositionality Benchmark for Video LLMs**](https://arxiv.org/abs/2602.00288) | Paired videos with similar static content and different temporal structure. | Offline paired-clip evaluation. | [Project, code, and data](https://baiqi-li.github.io/timeblind_project/) |
| 2025-05-23 | [**Daily-Omni: Towards Audio-Visual Reasoning with Temporal Alignment across Modalities**](https://arxiv.org/abs/2505.17862) | Cross-modal temporal alignment and audiovisual event reasoning. | Offline clip QA; classified here by its evaluation protocol. | [Project](https://lliar-liar.github.io/Daily-Omni/) · [Code and data](https://github.com/Lliar-liar/Daily-Omni) |
| 2025-02-06 | [**WorldSense: Evaluating Real-world Omnimodal Understanding for Multimodal LLMs**](https://arxiv.org/abs/2502.04326) | Synchronized audiovisual understanding with text/subtitle conditions. | Offline whole-clip QA. | [Project](https://jaaackhongggg.github.io/WorldSense/) · [Repository](https://github.com/JaaackHongggg/WorldSense) · [Dataset](https://huggingface.co/datasets/honglyhly/WorldSense) |
| 2024-10-14 | [**TemporalBench: Benchmarking Fine-grained Temporal Understanding for Multimodal Video Models**](https://arxiv.org/abs/2410.10818) | Event order, action frequency, motion magnitude, and temporal descriptions. | Offline video QA and captioning. | [Project, code, and data](https://temporalbench.github.io/) |
| 2024-09-23 | [**OmniBench: Towards The Future of Universal Omni-Language Models**](https://arxiv.org/abs/2409.15272) | Complementary image, audio, and text evidence. | Offline multimodal tuples; no continuous video stream. | [Project](https://m-a-p.ai/OmniBench/) · [Code and data](https://github.com/multimodal-art-projection/OmniBench) |

## Reading results critically

The following questions guide comparisons in this list:

| Aspect | What to report or check |
|:--|:--|
| **Causal access** | Which frames, audio samples, transcripts, subtitles, and user questions were available at each response time? Were ingestion or memory decisions conditioned on a future query? |
| **Memory and retrieval** | What persists between updates? Give active memory and archive sizes, retention horizon, retrieval cost, and whether original frames or audio can be replayed. |
| **Temporal and multimodal necessity** | Compare against recent-frame, single-frame, text/transcript-only, and modality-ablation baselines where applicable; use order/timing controls to expose shortcuts. |
| **Latency and throughput** | State hardware, resolution, frame/audio rate, chunk size, and concurrency. Measure observation-to-response delay and sustained processing, including queues, retrieval, and generation. |
| **Interaction** | Separate answer correctness from response timing, proactive decisions, interruption handling, and incorporation of evidence arriving during a response. |
| **Long-running behavior** | Track memory/storage growth, backlog, forgetting, and state corrections over time; separate recent-scene perception from long-range recall. |
| **Matched comparisons** | Match backbone, available modalities, observation budget, historical access, and evaluation protocol before attributing gains to a memory or reasoning mechanism. |

[SimpleStream](https://arxiv.org/abs/2604.02317) is a useful reminder to compare sophisticated memory systems against a recent-context baseline. A capability claim should identify what was demonstrated and what remains untested; benchmark accuracy alone does not establish a complete streaming assistant.

## Where to start

1. **Learn the streaming setup:** [VideoLLM-online](https://arxiv.org/abs/2406.11816), then [StreamingBench](https://arxiv.org/abs/2411.03628) and [OVO-Bench](https://arxiv.org/abs/2501.05510).
2. **Study what should persist:** compare [SimpleStream](https://arxiv.org/abs/2604.02317), [StreamForest](https://arxiv.org/abs/2509.24871), and [OmniMem](https://arxiv.org/abs/2606.07577).
3. **Connect streaming perception with agents:** read [DeltaStreamer](https://arxiv.org/abs/2610.19849), alongside transferable memory ideas from [A-MEM](https://arxiv.org/abs/2502.12110) and [MemGPT](https://arxiv.org/abs/2310.08560).
4. **Connect the modalities and interaction:** examine [Qwen3-Omni](https://arxiv.org/abs/2509.17765), [MiniCPM-o 4.5](https://arxiv.org/abs/2604.27393), and [VST](https://arxiv.org/abs/2603.12262), keeping synchronization, response timing, and full duplex distinct.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for entry formats and evidence requirements. Contributions should connect a work to at least one core question and explain its streaming capability or its role as a supporting component or diagnostic.

Works do not need to support all four input modalities. Please link primary sources, use first-submission dates consistently, and distinguish demonstrated behavior from proposed extensions.

## Related resources

- [Awesome Streaming Video Understanding](https://github.com/sotayang/Awesome-Streaming-Video-Understanding): a broader tracker of streaming/online video papers, code, and datasets.
- [Awesome Multimodal Large Language Models](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models): broader multimodal model context.
- [Awesome Unified Multimodal Models](https://github.com/ATH-MaaS/Awesome-Unified-Multimodal-Models): related understanding and generation research beyond this list's primary scope.

## Citation

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

## Contact

For questions, suggestions, or collaboration, contact **Yuanqing Wang** at [yuanqing.wang@utdallas.edu](mailto:yuanqing.wang@utdallas.edu).

## License

Unless otherwise noted, the original documentation and copyrightable curation in this repository are licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). Linked papers, datasets, models, and software retain their respective licenses.

When sharing or adapting material covered by CC BY 4.0, provide appropriate credit, link to the license, and indicate any changes. The BibTeX above is a suggested academic citation format. See the [official CC BY 4.0 summary](https://creativecommons.org/licenses/by/4.0/).

**Suggested attribution:** Yuanqing Wang and contributors, [Awesome Streaming Multimodal Understanding and Interaction](https://github.com/Wang-Yuanqing/Awesome-Streaming-Multimodal-Understanding-and-Interaction), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Indicate any modifications you make.
