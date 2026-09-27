# llmperf

LLMPerf — Ray Project tool for evaluating LLM API performance (throughput, latency) and correctness.

> Source in `llmperf-main/` (`token_benchmark_ray.py`, `llm_correctness.py`).

## Installation
```bash
cd llmperf-main
pip install -e .
```

## Basic Usage
Load test + correctness test:
```bash
python token_benchmark_ray.py
python llm_correctness.py
```

Analysis notebook: `analyze-token-benchmark-results.ipynb`.
Dev requirements: `requirements-dev.txt`, `pyproject.toml`.

## Tech
- Python, Ray, Jupyter

## License
See `LICENSE.txt` / `NOTICE.txt` (Ray Project).
