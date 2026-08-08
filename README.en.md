# TuringTest-Data

Turing-Test experiment data and scripts for the Semantic Echo project (Chinese Turing detection + emotion benchmarks).

> Main repo: [091635Aa/SemanticEcho](https://github.com/091635Aa/SemanticEcho)
> Showcase repo: [091635Aa/1.5B-Turing-Challenge](https://github.com/091635Aa/1.5B-Turing-Challenge)
> 中文版: [README.md](README.md)

## Contents

This repo hosts **the experiment data produced by the Semantic Echo engine** (results of 5 benchmarks, logs, scripts, and experiment records). It does **not** include third-party official datasets.

## Directory Layout

```
├── data/                          # Benchmark result files
│   ├── emocharacter_results.json          # EmoCharacter role-play emotional fidelity results
│   ├── feel_heart_results.json            # HEART-BENCH memory-driven personality inference results
│   ├── heartbench_results.json            # HeartBench Chinese "human-ness" benchmark results
│   ├── llm_judge_results.json             # LLM-as-Judge blind evaluation results
│   ├── turingbench_results.json           # TuringBench Chinese-system Turing detection results
│   ├── cross_model_comparison.json        # Cross-model comparison
│   ├── judge_bias_analysis.json           # Judge bias analysis
│   ├── replies_Qwen2.5-*.json             # Generated replies by model
│   └── 淘汰记录.json                        # Eliminated model records
├── repos/                        # HeartBench / HEART-BENCH official benchmark repos (runtime dependency)
├── logs/                         # Benchmark run logs
├── results/                      # summary.json + report.md
├── 实验/                         # Phase results & experiment logs
├── 0_准备数据.py                 # Data preparation script (official datasets downloaded separately)
├── run_*.py                      # Benchmark entry points
├── 公共模块.py / 生成器.py / 早停.py
└── 验证_*.py                     # Reproduction / judge-bias / cross-model scripts
```

> Note: Official datasets (TuringBench / HeartBench / HEART-BENCH) are **not** included in this repo
> (large, third-party data). Download them from each benchmark's official source before running,
> or follow `0_准备数据.py` to prepare the data.

## Usage

1. Download official benchmark datasets (e.g. TuringBench) and prepare data with `0_准备数据.py`
2. Run `run_turingbench.py` / `run_emocharacter.py` / `run_heartbench.py` / `run_feel_heart.py` / `run_llm_judge.py` to execute each benchmark
3. Run `run_all.py` to generate the summary report (`results/summary.json` + `results/报告.md`)
