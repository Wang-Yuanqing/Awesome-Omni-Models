# Contributing

This list studies **streaming multimodal understanding and interaction**: understanding text, images, video, and audio as observations arrive, maintaining relevant memory, and interacting through text and speech.

## Choose a section

Connect each contribution to at least one of the four core questions in [README.md](README.md#four-core-questions):

- **Temporal understanding:** actions, event order, identity, state changes, and temporal training signals.
- **Memory:** retention, updates, compression, retrieval, evidence archives, and transferable agent memory.
- **Cross-modal synchronization:** audiovisual/text alignment and multimodal foundations with relevant streaming mechanisms.
- **Online reasoning and interaction:** causal reasoning, multi-turn dialogue, response timing, proactive behavior, and concurrent perception and generation.

Benchmarks belong in the online/streaming or supporting offline section according to their protocol. Text-agent components, speech-only systems, and visual-only streaming methods are welcome when their relevance is explicit. Support for three or four modalities is not an entry requirement.

Image and video synthesis are outside the primary scope. A model with those capabilities may still qualify through a relevant understanding or interaction contribution.

## Add a source-backed entry

1. Link the primary paper or an official technical report. Verify the title and identifier against that source.
2. Use the **first arXiv submission date**, formatted YYYY-MM-DD, rather than a revision, conference, or repository-update date. If no arXiv paper exists, label the date as an official report/release date.
3. Place the work in its main section and sort rows by date, newest first. Cross-reference other sections when useful rather than duplicating the full entry.
4. Describe the mechanism and the scope demonstrated in the linked work. State relevant limits concisely.
5. Link official code, data, or project pages. Label projects as projects; a repository link alone does not establish available model weights or a complete implementation.
6. Explain in the pull request which core question the entry addresses and point to the source passage supporting its capability claim.

General method format:

~~~markdown
| YYYY-MM-DD | [**Exact paper title**](https://arxiv.org/abs/ID) | Mechanism, demonstrated scope, and relevant boundary. | [Code](https://github.com/OWNER/REPO) |
~~~

For multimodal foundations, add an **Inputs → outputs** column before the streaming-mechanism column. Use **T** for text, **I** for images, **V** for video, **A** for audio, and **S** for speech output. Speech is a subset of audio; do not count it as an additional independent modality.

For benchmarks, use **Date | Benchmark | Main focus | Protocol boundary | Resources**. State whether the protocol is causal/timestamped streaming, offline clip QA, or another explicitly described setting.

## Describe streaming precisely

- Distinguish **input ingestion**, **output streaming**, and **full-duplex interaction**. Fast or streaming speech output alone does not establish streaming video understanding.
- Distinguish **reactive answers**, **proactive responses**, and **interruption handling**.
- State whether memory persists across observations and whether retrieval accesses retained representations or replays archived source data.
- Treat frame/chunk sampling as an implementation choice. Describe the online state and causal protocol rather than using sampling frequency alone as a capability label.
- Keep offline diagnostics and transferable text-agent methods explicitly labeled; do not imply demonstrated audiovisual streaming support.
- Avoid unsupported architecture labels, inferred full-duplex capabilities, unqualified speed comparisons, and leaderboard numbers copied across different protocols.

## Before submitting

Check the row's title, first-submission date, primary-source link, official resources, section, and chronological order. Check table column counts and local section links. For corrections, identify the current claim, provide the replacement, and link the supporting source.

Keep summaries brief and original. Preserve the distinction between what the source demonstrates, our classification of its protocol, and an extension we would like to investigate.
