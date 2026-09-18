# GPT-5.6 advisor routing data

Snapshot date: 2026-09-11. This is a routing snapshot, not a claim that benchmarks predict every task. Scores from different benchmarks are not directly comparable; normalize only within each benchmark, and use the closest task/harness.

Sources:
- https://openai.com/index/gpt-5-6/
- https://openai.com/index/gpt-6-astra/
- https://developers.openai.com/api/docs/models
- https://help.openai.com/en/articles/11481834-chatgpt-rate-card

## Rates

Current API standard text-token prices per 1M tokens:

| Model | Input | Cached input | Output |
|---|---:|---:|---:|
| GPT-6 Astra | $10.00 | $1.00 | $50.00 |
| GPT-5.6 Sol | $4.00 | $0.40 | $20.00 |
| GPT-5.6 Terra | $2.00 | $0.20 | $12.00 |
| GPT-5.6 Luna | $0.20 | $0.02 | $1.20 |

Codex/Work rate-card credits per 1M tokens:

| Model | Input | Cached input | Output |
|---|---:|---:|---:|
| GPT-6 Astra | 250 | 25 | 1,250 |
| GPT-5.6 Sol | 100 | 10 | 500 |
| GPT-5.6 Terra | 50 | 5 | 300 |
| GPT-5.6 Luna | 5 | 0.5 | 30 |

For a task with `I` uncached input tokens, `K` cached input tokens, and `O` output tokens, calculate:

`cost(model) = (I × input_rate + K × cached_rate + O × output_rate) / 1,000,000`

Use credits for Codex routing and USD for API routing. Tool-call charges and fast-mode multipliers are separate and must be added when applicable.

## GPT-5.6 family benchmark snapshot

Scores are `Sol | Terra | Luna`. A dash means OpenAI did not publish a value in this table.

### Professional

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| Agents’ Last Exam | 52.7% | 50.4% | 50.3% |
| GDPval-AA v2 | 1,747.8 Elo | 1,593 Elo | 1,591.8 Elo |
| Management Consulting Tasks (Internal) | 43.2% | 37.2% | 35.4% |
| Big Finance Bench | 53% | 51% | 36% |
| Artificial Analysis Intelligence Index v4.1 | 58.9 | 55 | 51.2 |

### Coding

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| Artificial Analysis Coding Agent Index v1.1 | 80 | 77.4 | 74.6 |
| SWE-Bench Pro | 64.6% | 63.4% | 62.7% |
| DeepSWE v1.1 | 72.7% | 69.6% | 67.2% |
| Terminal-Bench 2.1 | 88.8% | 87.4% | 84.7% |

### Science and health

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| GeneBench Pro | 28.7% | 23.3% | 10.8% |
| LifeSciBench | 59.9% | 56% | 51.2% |
| MedChemBench (Internal) | 48.3% | 35% | 30.4% |
| HealthBench Professional | 60.5% | 57.7% | 55.7% |

### Computer use

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| OSWorld 2.0 | 62.6% | 50.2% | 45.6% |
| BrowseComp | 90.4% | 87.5% | 83.3% |
| BenchCAD | 70.6% | 62.3% | 63.1% |

### Cybersecurity

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| Capture-the-Flag Challenges | 96.7% | 91.8% | 85.2% |
| SEC-Bench Pro | 71.2% | 57.7% | 48.9% |
| ExploitBench | 73.5% | 52.9% | 33.2% |
| ExploitGym | 33.7% | 23.2% | 12.4% |

### Self-improvement and research

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| Internal Research Debugging Evaluation | 68.3% | 67.8% | 50.8% |
| KernelGen 1P | 61.1% | 49.2% | 22.4% |
| NanoGPT | 9.69% | 14.5% | 1.66% |
| PostTrainBench Lite | 50.3% | 51.5% | 29.6% |
| RSI Index | 57.9% | 56.3% | 41.9% |

### Multimodal

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| MMMU Pro (no tools) | 83% | 80.7% | 78.4% |
| MMMU Pro (with tools) | 84.6% | 82% | 79.5% |
| gdp.pdf | 30.7% | 24.7% | 22.7% |

### Academic

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| GPQA Diamond | 94.6% | 92.9% | 92.3% |
| FrontierMath Tier 1–3 (v2) | 89% | 84.9% | 78.6% |
| FrontierMath Tier 4 (v2) | 83% | 68.3% | 58.5% |

### Tool use

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| AutomationBench | 18.1% | 15.2% | 14.9% |
| Toolathlon | 58% | 53.1% | 53.4% |

### Long context

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| OpenAI MRCR v2 8-needle 256K–512K | 91.5% | 89.6% | 41.3% |
| OpenAI MRCR v2 8-needle 512K–1M | 73.8% | 72.5% | 41.3% |
| GraphWalks BFS 256K F1 | 90.7% | 76.9% | 81.3% |
| GraphWalks BFS 1M F1 | 77.1% | 71.2% | 51.2% |

### Abstract reasoning

| Benchmark | Sol | Terra | Luna |
|---|---:|---:|---:|
| ARC-AGI-3 | 7.78% | 0.8% | 0.18% |

## GPT-6 Astra benchmark snapshot

These are from a newer Astra publication with a different benchmark set and harness. Do not merge them into GPT-5.6 aggregate scores unless the benchmark name and protocol match exactly. Values are `Astra | Sol`; Terra and Luna were not published in this table.

| Domain | Benchmark | Astra | Sol |
|---|---|---:|---:|
| Computer use | Agents’ Last Exam | 59.3% | 53.6% |
| Computer use | OSWorld 2.0 (v2026.08.08, partial score) | 72.6% | 65.7% |
| Computer use | ScreenSpot-Pro (no tools) | 92.7% | 76.9% |
| Professional | AutomationBench | 41.4% | 18.1% |
| Professional | BenchCAD | 95.9% | 83.3% |
| Professional | BrowseComp | 91.5% | 90.4% |
| Professional | OpenScore String Quartets | 0.84 | 0.19 |
| Professional | Internal Design Tasks | 50.0% | 47.4% |
| Professional | Internal Data Science Tasks | 40.9% | 30.5% |
| Professional | Artificial Analysis Intelligence Index v4.1.1 | 61.2 | 60.9 |
| Coding | Terminal-Bench 4.0 | 57.9% | 37.3% |
| Coding | DeepSWE v1.1 | 74.1% | 72.7% |
| Coding | FrontierCode 1.1 Extended | 64.5% | 60.6% |
| Coding | FrontierCode 1.1 Main | 53.3% | 47.5% |
| Coding | Internal Database Migration Tasks | 63.9% | 42.7% |
| Coding | Artificial Analysis Coding Agent Index v1.4 | 67.0 | 65.1 |
| Academic | Terminal-Bench Science 0.1 | 64.6% | 22.4% |
| Academic | FrontierMath Tier 4 (v2) | 97.6% | 83.0% |
| Academic | GPQA Diamond | 96.0% | 94.6% |
| Academic | Humanity’s Last Exam (with tools) | 57.2% | — |
| Science and health | GeneBench Pro | 37.1% | 32.3% |
| Science and health | MedChemBench (Internal) | 49.3% | 47.4% |
| Science and health | LifeSciBench | 60.3% | 59.9% |
| Science and health | HealthBench Professional (length-adjusted) | 63.4% | 60.5% |
| Cybersecurity | ExploitBench | 100.0% | 78.5% |
| Cybersecurity | ExploitGym | 42.4% | 30.3% |
| Cybersecurity | ExploitBench (June–August 2026) | 39.0% | 5.5% |
| Cybersecurity | SRE-Bench | 88.0% | 55.9% |
| Cybersecurity | SEC-Bench Pro | 85.4% | 79.1% |
| Alignment | Internal computer-use safety benchmark (lower is better) | 2.4% | 22.0% |

For the alignment metric, lower is better. Use it as a hard safety signal, not as a quality score.