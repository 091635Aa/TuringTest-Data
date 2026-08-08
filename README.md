# TuringTest-Data

语义回响（Semantic Echo）项目图灵测试实验数据与脚本。

> 主仓库：[091635Aa/SemanticEcho](https://github.com/091635Aa/SemanticEcho)
> 展示仓库：[091635Aa/1.5B-Turing-Challenge](https://github.com/091635Aa/1.5B-Turing-Challenge)
> English: [README.en.md](README.en.md)

## 仓库内容

本仓库存放**语义回响引擎的图灵测试实验数据**（5 项基准的测试结果、日志、脚本与实验记录），不含第三方官方数据集。

## 目录结构

```
├── data/                          # 各基准实验结果
│   ├── emocharacter_results.json          # EmoCharacter 角色扮演情感保真度结果
│   ├── feel_heart_results.json            # HEART-BENCH 记忆驱动人格推理结果
│   ├── heartbench_results.json            # HeartBench 中文人味儿评测结果
│   ├── llm_judge_results.json             # LLM-as-Judge 裁判盲评结果
│   ├── turingbench_results.json           # TuringBench 中文体系图灵检测结果
│   ├── cross_model_comparison.json        # 多模型横向对比
│   ├── judge_bias_analysis.json           # 裁判偏差分析
│   ├── replies_Qwen2.5-*.json             # 各模型生成回复样本
│   └── 淘汰记录.json
├── repos/                        # HeartBench / HEART-BENCH 官方基准仓库（运行依赖）
├── logs/                         # 各基准运行日志
├── results/                      # summary.json + 报告.md（汇总判定）
├── 实验/                         # 阶段结果与实验记录
├── 0_准备数据.py                 # 数据准备脚本（需自行下载官方数据集）
├── run_*.py                      # 各基准测试入口
├── 公共模块.py / 生成器.py / 早停.py
└── 验证_*.py                     # 复现验证 / 裁判偏差 / 多模型对比脚本
```

> 注：TuringBench / HeartBench / HEART-BENCH 等**官方数据集**不在此仓库（体积大且为第三方数据），
> 运行测试前请从各基准官方源下载，或按 `0_准备数据.py` 中的说明准备。

## 使用方法

1. 从官方源下载基准数据集（TuringBench 等），按 `0_准备数据.py` 准备数据
2. 运行 `run_turingbench.py` / `run_emocharacter.py` / `run_heartbench.py` / `run_feel_heart.py` / `run_llm_judge.py` 执行各基准
3. 运行 `run_all.py` 生成汇总报告（`results/summary.json` + `results/报告.md`）
