# Datasets

Preference datasets used for DPO training and mask calibration. Dataset keys are resolved by
[`src/utils/dataset_registry.py`](../utils/dataset_registry.py).

| Domain | Dataset | Hugging Face ID |
|---|---|---|
| Instruction following | Tulu 3 DPO mixture | [`allenai/llama-3.1-tulu-3-8b-preference-mixture`](https://huggingface.co/datasets/allenai/llama-3.1-tulu-3-8b-preference-mixture) |
| Math | Math-Step-DPO-10K | [`xinlai/Math-Step-DPO-10K`](https://huggingface.co/datasets/xinlai/Math-Step-DPO-10K) |
| Math / reasoning | Light-R1-DPOData | [`qihoo360/Light-R1-DPOData`](https://huggingface.co/datasets/qihoo360/Light-R1-DPOData) |
| Coding | Code-Preference-Pairs | [`Vezora/Code-Preference-Pairs`](https://huggingface.co/datasets/Vezora/Code-Preference-Pairs) |

## Notes

- **Tulu 3** is the default instruction-following mixture and the canonical case for the
  end-to-end pipeline.
- **Math-Step-DPO-10K** carries a leading reasoning field from a chain-of-thought paper. That field
  can be ignored — the `chosen` / `rejected` pair is compatible with standard DPO as-is.
- **Light-R1-DPOData** is the default in several scripts and doubles as an alternative math source.
- **Code-Preference-Pairs** covers the coding domain.

GRPO uses Open-R1 Math rather than a preference dataset; see
[`docs/GRPO_OPEN_R1_RUNBOOK.md`](../../docs/GRPO_OPEN_R1_RUNBOOK.md).
