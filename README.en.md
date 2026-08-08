# TuringTest-Data

Complete Turing-Test dataset for the Semantic Echo project (Chinese Turing detection + emotion benchmarks).

> Main repo: [091635Aa/SemanticEcho](https://github.com/091635Aa/SemanticEcho)
> Showcase repo: [091635Aa/1.5B-Turing-Challenge](https://github.com/091635Aa/1.5B-Turing-Challenge)
> 中文版: [README.md](README.md)

## Directory Layout

```
├── data/
│   ├── turingbench.zip        # ⚠️ Oversized file (228MB) -> download from Release
│   ├── turingbench/           # Extracted TuringBench data
│   │   ├── TuringBench/
│   │   │   ├── AA/            # Human-written text (train.csv 135MB via Release; test/valid in repo)
│   │   │   └── TT_*/          # Machine text: GPT-1/GPT-2/GPT-3/Grover/XLNet/Transfo-XL/XLM etc.
│   ├── emocharacter_results.json      # EmoCharacter role-play emotional fidelity results
│   ├── feel_heart_results.json        # HEART-BENCH memory-driven personality inference results
│   ├── heartbench_results.json        # HeartBench Chinese "human-ness" benchmark results
│   ├── llm_judge_results.json         # LLM-as-Judge blind evaluation results
│   ├── turingbench_results.json       # TuringBench Chinese-system Turing detection results
│   ├── cross_model_comparison.json    # Cross-model comparison
│   ├── judge_bias_analysis.json       # Judge bias analysis
│   └── 淘汰记录.json                    # Eliminated model records
├── repos/                     # HeartBench / HEART-BENCH official benchmark repos
├── logs/                      # Benchmark run logs
├── results/                   # summary.json + report.md
├── 实验/                       # Phase results & experiment logs
├── 0_准备数据.py              # Data preparation script
├── run_*.py                   # Benchmark entry points
├── 公共模块.py / 生成器.py / 早停.py
└── 验证_*.py                  # Reproduction / judge-bias / cross-model scripts
```

## ⚠️ Oversized Files (>100MB, git limit)

These files exceed GitHub's 100MB per-file push limit, so they live in **Release v1.0.0**:

| File | Size | Release asset name | Description |
|---|---|---|---|
| `data/turingbench.zip` | 228MB | `turingbench.zip` | Official TuringBench data archive |
| `data/turingbench/TuringBench/AA/train.csv` | 135MB | `AA_train.csv` | Human-annotated training set |

**Download:** [Release v1.0.0](https://github.com/091635Aa/TuringTest-Data/releases/tag/v1.0.0)

Place them back to restore the full dataset:

```
turingbench.zip   ->  data/turingbench.zip
AA_train.csv      ->  data/turingbench/TuringBench/AA/train.csv
```

## Usage

1. Download the oversized files from Release and restore their paths
2. Run `0_准备数据.py` to prepare data
3. Run `run_turingbench.py` / `run_emocharacter.py` / `run_heartbench.py` / `run_feel_heart.py` / `run_llm_judge.py` to execute each benchmark
4. Run `run_all.py` to generate the summary report (`results/summary.json` + `results/报告.md`)
