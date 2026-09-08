# Example: Feature-only PR

This accepted-style example uses historical GenEval2 results. Adapt the structure, not its project-specific facts. The outer four-backtick fence is for chat delivery; a saved `.md` body contains only its contents.

````markdown
## Summary

Integrate GenEval2 into IGEvalKit for text-to-image generation and evaluation.

Reference paper: [GenEval2 (arXiv:2512.16853)](https://arxiv.org/abs/2512.16853)

Origin GitHub repo: [facebookresearch/GenEval2](https://github.com/facebookresearch/GenEval2)

## What's changed

### feat

- Add the official GenEval2 data (800 prompts) and benchmark configuration.
- Integrate prompt export, Qwen3-VL-based VQA judging, and Soft-TIFA scoring into IGEvalKit.
- Support resumable evaluation with prompt-level scores and skill/atomicity summaries.

## Results

Recorded run (2026-09-07): 800 prompts, 2048 x 2048 images, `Qwen3-VL-8B-Instruct` judge. Scores use a 0-100 scale; Soft-TIFA GM is primary. This run predates subsequent judge-token changes and has not been rerun.

| Model | Soft-TIFA GM | Soft-TIFA AM |
| --- | ---: | ---: |
| U15-10500-info-mt20k-sft27k | 54.42 | 86.84 |

## Tips

- In `sweep_ckpts_neo_u15.py`, add `"geneval2"` to `BENCHES` and `"geneval2": "SS_BASE_CONFIG"` to `BENCH_BASE_CONFIGS` for square image generation.
- Set `judge_model_path` and `judge_python` in `geneval2.yaml` for the target environment.
- Generation uses only `prompt`; VQA judging uses the generated image and the corresponding `vqa_list`.

After configuring the sweep script, submit a 2K run from the repository root:

```bash
python zoe_eval/scripts/eval_scripts/u15/sweep_ckpts_neo_u15.py \
  --mode submit \
  --resolution 2k
```
````
