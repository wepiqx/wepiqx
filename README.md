# wepiqx — independent GGUF quantization developer

I build open quantization tooling and hand-tuned GGUF models on consumer hardware. Measure first, crown with tasks, keep every scar in the ledger.

## What I do

- **MERNIK** — measure-first quantization protocol: imatrix-driven priority-queue allocation with a strict split between allocator signals (fast ring: PPL canary, KLD rank column) and capability certification (slow ring: HumanEval / EvalPlus, fixed seeds). Code: [`wepiqx/MERNIK`](https://github.com/wepiqx/MERNIK)
- **RINIQ** — layer-interleaved tri-fusions of Qwen3.5-9B finetunes (OxCoder + Ornith + NeoHorse), quantized by MERNIK. Crown: 92.07% HumanEval at 5.0 GB
- **SHQ series** — selective hybrid quantization for 8 GB Pascal GPUs (GTX 1070): IQ4_XS on FFN + Q8_0 boundary attention, beating stock flat quants on perplexity and coding quality

## Models (Hugging Face)

- [RINIQ-MERNIK-GGUF](https://huggingface.co/wepiqx/RINIQ-MERNIK-GGUF) — tri-fusion 9B quants
- [OxCoder-9B-MERNIK-GGUF](https://huggingface.co/wepiqx/OxCoder-9B-MERNIK-GGUF) — agentic code distillate quants
- [NeoHorse-1-9B-MERNIK-GGUF](https://huggingface.co/wepiqx/NeoHorse-1-9B-MERNIK-GGUF) — thinking-model quants
- [gemma-4-12B-it-SHQ6-GGUF](https://huggingface.co/wepiqx/gemma-4-12B-it-SHQ6-GGUF) — first repo: Gemma 4 12B IQ-hybrid for Pascal
- [gemma-4-12B-OBLITERATED-SHQ7-GGUF](https://huggingface.co/wepiqx/gemma-4-12B-OBLITERATED-SHQ7-GGUF) — uncensored SHQ7

Full model list: [huggingface.co/wepiqx](https://huggingface.co/wepiqx)

## Protocol in one paragraph

Allocator signals never certify; capability scores never steer. Every claim ships three columns (PPL canary, KLD rank, task verdict) or stays unverified. Full ledger in [`wepiqx/MERNIK`](https://github.com/wepiqx/MERNIK) (`README.md`, `FUSION.md`, `README-ZOO.md`, `SAGA.md`).

License for my code: Apache-2.0.
