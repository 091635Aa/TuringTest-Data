# TuringTest-Data

语义回响（Semantic Echo）项目图灵测试完整数据集。

> 主仓库：[091635Aa/SemanticEcho](https://github.com/091635Aa/SemanticEcho)
> 展示仓库：[091635Aa/1.5B-Turing-Challenge](https://github.com/091635Aa/1.5B-Turing-Challenge)
> English: [README.en.md](README.en.md)

## 目录结构

```
├── data/
│   ├── turingbench.zip        # ⚠️ 超大文件（228MB），见下方 Release 下载
│   ├── turingbench/           # TuringBench 解压后的数据
│   │   ├── TuringBench/
│   │   │   ├── AA/            # 人工标注（train.csv 135MB 走 Release，test/valid 在仓库）
│   │   │   └── TT_*/          # GPT-1/GPT-2/GPT-3/Grover/XLNet/Transfo-XL/XLM 等机器文本
│   ├── emocharacter_results.json      # EmoCharacter 角色扮演情感保真度结果
│   ├── feel_heart_results.json        # HEART-BENCH 记忆驱动人格推理结果
│   ├── heartbench_results.json        # HeartBench 中文人味儿评测结果
│   ├── llm_judge_results.json         # LLM-as-Judge 裁判盲评结果
│   ├── turingbench_results.json       # TuringBench 中文体系图灵检测结果
│   ├── cross_model_comparison.json    # 多模型横向对比
│   ├── judge_bias_analysis.json       # 裁判偏差分析
│   └── 淘汰记录.json
├── repos/                     # HeartBench / HEART-BENCH 官方基准仓库
├── logs/                      # 各基准运行日志
├── results/                   # summary.json + 报告.md
├── 实验/                       # 阶段结果与实验记录
├── 0_准备数据.py              # 数据准备脚本
├── run_*.py                   # 各基准测试入口
├── 公共模块.py / 生成器.py / 早停.py
└── 验证_*.py                  # 复现验证 / 裁判偏差 / 多模型对比脚本
```

## ⚠️ 超大文件（>100MB，git 无法承载）

以下文件因超过 GitHub 单文件 100MB 推送限制，存放在 **Release v1.0.0**：

| 文件 | 大小 | Release 中的名称 | 说明 |
|---|---|---|---|
| `data/turingbench.zip` | 228MB | `turingbench.zip` | TuringBench 官方数据压缩包 |
| `data/turingbench/TuringBench/AA/train.csv` | 135MB | `AA_train.csv` | 人工标注训练集 |

**下载：** [Release v1.0.0](https://github.com/091635Aa/TuringTest-Data/releases/tag/v1.0.0)

下载后按上方路径放回即可还原完整数据集：

```
turingbench.zip   ->  data/turingbench.zip
AA_train.csv      ->  data/turingbench/TuringBench/AA/train.csv
```

## 使用说明

1. 下载 Release 中的超大文件并放回对应路径
2. 运行 `0_准备数据.py` 准备数据
3. 运行 `run_turingbench.py` / `run_emocharacter.py` / `run_heartbench.py` / `run_feel_heart.py` / `run_llm_judge.py` 执行各基准
4. 运行 `run_all.py` 生成汇总报告（`results/summary.json` + `results/报告.md`）
