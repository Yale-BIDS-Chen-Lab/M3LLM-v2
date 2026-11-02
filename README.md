# M3LLM

**From Compound Figures to Medical Multi-image Reasoning: Scaling Multimodal Large Language Models with Biomedical Literature**

M3LLM is a medical multimodal language model developed for reasoning across multiple images. This repository contains the PMC-MI instruction-construction pipeline, the three-stage post-training recipes, and the evaluation code accompanying the [updated preprint](https://arxiv.org/abs/2511.22232v2).

- **Updated preprint:** [arXiv:2511.22232v2](https://arxiv.org/abs/2511.22232v2) · [PDF](https://arxiv.org/pdf/2511.22232v2)
- **Data and benchmark:** [PMC-MI and PMC-MI-Bench](https://huggingface.co/datasets/Yale-BIDS-Chen/M3LLM-data-v1.0.0)
- **Versioned code:** [v1.0.2](https://github.com/Yale-BIDS-Chen-Lab/M3LLM-v2/tree/v1.0.2)
- **Upstream source resource:** [MedPMC](https://github.com/Yale-BIDS-Chen-Lab/MedPMC)

**29 September 2026:** The revised preprint is available, with the three-stage training framework, expanded benchmark and clinical evaluations, and independent medical-reviewer assessments.

## Quick start

1. Explore [DataConstruction](DataConstruction/README.md) for the five-step PMC-MI workflow, exact prompts, and example commands.
2. See [Training](Training/README.md) for multi-image SFT, selection-aware policy refinement, and full-mixture SFT.
3. See [Evaluation](Evaluation/README.md) for PMC-MI-Bench, public benchmarks, response-quality assessment, and clinical-validation scripts.

Install dependencies within the relevant component rather than at the repository root. The released data and benchmark are hosted separately on Hugging Face.

## Workflow

| Component | Purpose | Location |
| --- | --- | --- |
| PMC-MI construction | Build task-specific instructions from compound figures and article context | [`DataConstruction/`](DataConstruction/README.md) |
| Stage I: MI-SFT | Multi-image supervised fine-tuning | [`Training/SFT/`](Training/README.md#stage-i-and-stage-iii-supervised-fine-tuning) |
| Stage II: GRPO | Selection-aware policy refinement | [`Training/GRPO/`](Training/README.md#stage-ii-policy-refinement) |
| Stage III: Full-SFT | Full-mixture supervised fine-tuning | [`Training/SFT/`](Training/README.md#stage-i-and-stage-iii-supervised-fine-tuning) |
| Evaluation | Benchmark and validation workflows | [`Evaluation/`](Evaluation/README.md) |

## Repository structure

```text
M3LLM-v2/
├── DataConstruction/   # Five-step pipeline and task-specific prompts
├── Training/           # SFT configurations and GRPO reward/training code
└── Evaluation/         # PMC-MI-Bench, public benchmarks, judge, and validations
```

The Yale New Haven Hospital (YNHH) dermatology cohort is not distributed here. Its aggregate results and evaluation procedures are described in the manuscript.

## Licence

Original M3LLM-v2 code and documentation are released under the [Apache License 2.0](LICENSE), consistent with MedPMC. This code licence does not cover the dataset, PMC article content, model weights, or third-party software. See [licensing details](docs/licensing.md), the [dataset card](https://huggingface.co/datasets/Yale-BIDS-Chen/M3LLM-data-v1.0.0), and [third-party notes](THIRD_PARTY.md).

## Citation

If you use M3LLM, PMC-MI, or PMC-MI-Bench, please cite the paper:

```bibtex
@article{chen2025m3llm,
  title={From Compound Figures to Medical Multi-image Reasoning: Scaling Multimodal Large Language Models with Biomedical Literature},
  author={Chen, Zhen and Fu, Yihang and Zhou, Rong and Applebaum, Serina and Kim, Min Kyu and Gilson, Aidan and Lee, Morten and Mirza, Salahudeen and Madera, Gabriel and Giuffre, Mauro and Pan, Yuanting and Jiang, Roy and Kim, Hyunjae and Xu, Hua and Chen, Qingyu},
  journal={arXiv preprint arXiv:2511.22232},
  year={2025},
  eprint={2511.22232},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  url={https://arxiv.org/abs/2511.22232v2},
  note={Version 2, revised 29 September 2026}
}
```
