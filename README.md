<div align="center"> <h1 style="font-size: 3em; margin-bottom: 0.2em;">Awesome-Omni-Models</h1> </div>

<div align="center">

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![GitHub last commit](https://img.shields.io/github/last-commit/Wang-Yuanqing/Awesome-Omni-Models)
![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

</div>

A curated list of **omni-modal models** spanning **any-to-text** and **any-to-any** architectures across text, image, audio, and video.

---

## 👉 What is This Repo for?

This repository tracks models that handle **three or more modalities** (text, image, audio, video) within a single system. We organize them along two axes the field actually uses:

- **By capability** — *Any-to-Any* (perceive **and** generate multiple modalities) vs. *Omni-Perception / Any-to-Text* (perceive many modalities, output text and/or speech).
- **By architecture** — **Native** models train all modalities jointly from scratch in one unified stream (early-fusion); **non-native** models graft pretrained modality encoders onto an LLM (late-fusion).

> **A quick taxonomy note.** "Any-to-any" specifically means multiple input *and* output modalities — though not every any-to-any model supports every modality on both ends. "Native" is an orthogonal training/architecture property, marked in the **Native?** column rather than split into its own section.

## 📖 Table of Contents

- [Surveys](#surveys)
- [Any-to-Any Models](#any-to-any-models)
- [Omni-Perception Models (Any-to-Text)](#omni-perception-models-any-to-text)
- [Benchmarks & Datasets](#benchmarks--datasets)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)
- [License](#license)

**Legend.** *In→Out* modalities: **T** = text, **I** = image, **A** = audio, **V** = video, **S** = speech. *Native?* ✅ = early-fusion / trained jointly from scratch, ➖ = late-fusion / grafted encoders, — = unknown / proprietary.

---

## Surveys

| Title | Venue | Date | Code |
|:------|:-----:|:----:|:----:|
| [**Unified Multimodal Understanding and Generation Models: Advances, Challenges, and Opportunities**](https://arxiv.org/abs/2505.02567) | arXiv | 2025-05-05 | [Project](https://github.com/AIDC-AI/Awesome-Unified-Multimodal-Models) |
| [**Scaling Laws for Native Multimodal Models**](https://arxiv.org/abs/2504.07951) | arXiv | 2025-04-10 | - |
| [**A Survey on Multimodal Large Language Models**](https://arxiv.org/abs/2306.13549) | NSR | 2024-06-23 | [Project](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models) |

## Any-to-Any Models

Models that both perceive and generate across multiple modalities.

| Title | In→Out | Native? | Venue | Date | Code | Demo |
|:------|:------:|:-------:|:-----:|:----:|:----:|:----:|
| ![Star](https://img.shields.io/github/stars/QwenLM/Qwen3-Omni.svg?style=social&label=Star) <br> [**Qwen3-Omni Technical Report**](https://arxiv.org/abs/2509.17765) | T,I,A,V→T,S | ✅ | arXiv | 2025-09-22 | [Github](https://github.com/QwenLM/Qwen3-Omni) | [Demo](https://huggingface.co/spaces/Qwen/Qwen3-Omni-Demo) |
| ![Star](https://img.shields.io/github/stars/baaivision/Emu3.5.svg?style=social&label=Star) <br> [**Emu3.5: Native Multimodal Models are World Learners**](https://arxiv.org/abs/2510.26583) | T,I,V→T,I,V | ✅ | arXiv | 2025-10-30 | [Github](https://github.com/baaivision/Emu3.5) | - |
| [**NExT-OMNI: Towards Any-to-Any Omnimodal Foundation Models with Discrete Flow Matching**](https://arxiv.org/abs/2510.13721) | T,I,A,V→T,I,A,V | ✅ | arXiv | 2025-10-16 | - | - |
| ![Star](https://img.shields.io/github/stars/ByteDance-Seed/Bagel.svg?style=social&label=Star) <br> [**BAGEL: Emerging Properties in Unified Multimodal Pretraining**](https://arxiv.org/abs/2505.14683) | T,I→T,I | ✅ | arXiv | 2025-05-20 | [Github](https://github.com/ByteDance-Seed/Bagel) | [Demo](https://demo.bagel-ai.org/) |
| ![Star](https://img.shields.io/github/stars/QwenLM/Qwen2.5-Omni.svg?style=social&label=Star) <br> [**Qwen2.5-Omni Technical Report**](https://github.com/QwenLM/Qwen2.5-Omni) | T,I,A,V→T,S | ✅ | Qwen | 2025-03-26 | [Github](https://github.com/QwenLM/Qwen2.5-Omni) | [Demo](https://huggingface.co/spaces/Qwen/Qwen2.5-Omni-7B-Demo) |
| [**GPT-4o Native Image Generation (System Card Addendum)**](https://cdn.openai.com/11998be9-5319-4302-bfbf-1167e093f1fb/Native_Image_Generation_System_Card.pdf) | T,I,A→T,I,A,S | — | OpenAI | 2025-03-25 | - | - |
| ![Star](https://img.shields.io/github/stars/baaivision/Emu3.svg?style=social&label=Star) <br> [**Emu3: Next-Token Prediction is All You Need**](https://arxiv.org/abs/2409.18869) | T,I,V→T,I,V | ✅ | arXiv | 2024-09-27 | [Github](https://github.com/baaivision/Emu3) | - |
| ![Star](https://img.shields.io/github/stars/facebookresearch/chameleon.svg?style=social&label=Star) <br> [**Chameleon: Mixed-Modal Early-Fusion Foundation Models**](https://arxiv.org/abs/2405.09818) | T,I→T,I | ✅ | arXiv | 2024-05-17 | [Github](https://github.com/facebookresearch/chameleon) | - |
| [**Transfusion: Predict the Next Token and Diffuse Images with One Multi-Modal Model**](https://arxiv.org/abs/2408.11039) | T,I→T,I | ✅ | arXiv | 2024-08-20 | - | - |
| ![Star](https://img.shields.io/github/stars/showlab/Show-o.svg?style=social&label=Star) <br> [**Show-o: One Single Transformer to Unify Multimodal Understanding and Generation**](https://arxiv.org/abs/2408.12528) | T,I→T,I | ✅ | arXiv | 2024-08-22 | [Github](https://github.com/showlab/Show-o) | - |
| ![Star](https://img.shields.io/github/stars/OpenMOSS/AnyGPT.svg?style=social&label=Star) <br> [**AnyGPT: Unified Multimodal LLM with Discrete Sequence Modeling**](https://arxiv.org/abs/2402.12226) | T,I,A,S→T,I,A,S | ✅ | arXiv | 2024-02-19 | [Github](https://github.com/OpenMOSS/AnyGPT) | - |
| ![Star](https://img.shields.io/github/stars/allenai/unified-io-2.svg?style=social&label=Star) <br> [**Unified-IO 2: Scaling Autoregressive Multimodal Models with Vision, Language, Audio, and Action**](https://arxiv.org/abs/2312.17172) | T,I,A,V→T,I,A | ✅ | CVPR | 2023-12-28 | [Github](https://github.com/allenai/unified-io-2) | - |
| ![Star](https://img.shields.io/github/stars/NExT-GPT/NExT-GPT.svg?style=social&label=Star) <br> [**NExT-GPT: Any-to-Any Multimodal LLM**](https://arxiv.org/abs/2309.05519) | T,I,A,V→T,I,A,V | ➖ | ICML | 2023-09-11 | [Github](https://github.com/NExT-GPT/NExT-GPT) | - |

## Omni-Perception Models (Any-to-Text)

Models that perceive many modalities but output text (and optionally speech).

| Title | In→Out | Native? | Venue | Date | Code | Demo |
|:------|:------:|:-------:|:-----:|:----:|:----:|:----:|
| ![Star](https://img.shields.io/github/stars/OpenBMB/MiniCPM-o.svg?style=social&label=Star) <br> [**MiniCPM-o 2.6: A GPT-4o Level MLLM on Your Phone**](https://github.com/OpenBMB/MiniCPM-o) | T,I,A,V→T,S | ➖ | Blog | 2025-01-13 | [Github](https://github.com/OpenBMB/MiniCPM-o) | [Demo](https://minicpm-omni.openbmb.cn/) |
| ![Star](https://img.shields.io/github/stars/NVlabs/OmniVinci.svg?style=social&label=Star) <br> [**OmniVinci: Enhancing Architecture and Data for Omni-Modal Understanding LLM**](https://arxiv.org/abs/2510.15870) | T,I,A,V→T | ➖ | arXiv | 2025-10-17 | [Github](https://github.com/NVlabs/OmniVinci) | - |
| ![Star](https://img.shields.io/github/stars/SenseTime-FVG/InteractiveOmni.svg?style=social&label=Star) <br> [**InteractiveOmni: A Unified Omni-modal Model for Audio-Visual Multi-turn Dialogue**](https://arxiv.org/abs/2510.13747) | T,I,A,V→T,S | ➖ | arXiv | 2025-10-15 | [Github](https://github.com/SenseTime-FVG/InteractiveOmni) | - |
| ![Star](https://img.shields.io/github/stars/Ola-Omni/Ola.svg?style=social&label=Star) <br> [**Ola: Pushing the Frontiers of Omni-Modal Language Model with Progressive Modality Alignment**](https://arxiv.org/abs/2502.04328) | T,I,A,V→T,S | ➖ | arXiv | 2025-02-06 | [Github](https://github.com/Ola-Omni/Ola) | - |
| ![Star](https://img.shields.io/github/stars/westlake-baichuan-mllm/bc-omni.svg?style=social&label=Star) <br> [**Baichuan-Omni-1.5 Technical Report**](https://arxiv.org/abs/2501.15368) | T,I,A,V→T,S | ➖ | arXiv | 2025-01-26 | [Github](https://github.com/westlake-baichuan-mllm/bc-omni) | - |
| ![Star](https://img.shields.io/github/stars/VITA-MLLM/VITA.svg?style=social&label=Star) <br> [**VITA-1.5: Towards GPT-4o Level Real-Time Vision and Speech Interaction**](https://arxiv.org/abs/2501.01957) | T,I,A,V→T,S | ➖ | NeurIPS | 2025-01-03 | [Github](https://github.com/VITA-MLLM/VITA) | - |
| ![Star](https://img.shields.io/github/stars/bytedance/SALMONN.svg?style=social&label=Star) <br> [**video-SALMONN: Speech-Enhanced Audio-Visual Large Language Models**](https://arxiv.org/abs/2406.15704) | I,A,V→T | ➖ | ICML | 2024-06-22 | [Github](https://github.com/bytedance/SALMONN) | - |
| ![Star](https://img.shields.io/github/stars/VITA-MLLM/VITA.svg?style=social&label=Star) <br> [**VITA: Towards Open-Source Interactive Omni Multimodal LLM**](https://arxiv.org/abs/2408.05211) | T,I,A,V→T,S | ➖ | arXiv | 2024-08-09 | [Github](https://github.com/VITA-MLLM/VITA) | - |

## Benchmarks & Datasets

| Title | Venue | Date | Code |
|:------|:-----:|:----:|:----:|
| [**WorldSense: Evaluating Real-world Omnimodal Understanding for Multimodal LLMs**](https://arxiv.org/abs/2502.04326) | arXiv | 2025-02-06 | [Project](https://jaaackhongggg.github.io/WorldSense/) |
| [**Daily-Omni: Towards Audio-Visual Reasoning with Temporal Alignment**](https://arxiv.org/abs/2505.17862) | arXiv | 2025-05-23 | - |
| [**OmniBench: Towards The Future of Universal Omni-Language Models**](https://arxiv.org/abs/2409.15272) | arXiv | 2024-09-23 | [Project](https://m-a-p.ai/OmniBench/) |

## Related Awesome Lists

- [Awesome-Unified-Multimodal-Models](https://github.com/AIDC-AI/Awesome-Unified-Multimodal-Models) — unified understanding + generation (image–text focus).
- [Awesome-Multimodal-Large-Language-Models](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models) — broad MLLM tracker.

## Contributing

Contributions are very welcome! To add a model:

1. Fork the repo and edit `README.md`.
2. Add a row to the **correct section** (Any-to-Any vs. Omni-Perception) in **reverse-chronological order**.
3. Use the column format: `Title (with paper link + star badge) | In→Out | Native? | Venue | Date | Code | Demo`.
4. Fill the **In→Out** and **Native?** fields accurately — these are the columns that make this list useful.
5. Open a PR with a one-line justification.

Please only submit models covering **three or more modalities**. Pure vision-language (image+text only) models belong in [Awesome-Unified-Multimodal-Models](https://github.com/AIDC-AI/Awesome-Unified-Multimodal-Models) instead.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work (CC0 1.0 Universal).
