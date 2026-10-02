# llmperf-main

LLMPerf — a toolkit for evaluating the performance and correctness of LLM APIs. It runs a **load test** (inter-token latency, generation throughput under concurrent requests) and a **correctness test** against OpenAI-compatible LLM endpoints, powered by Ray.

> Project source lives in `llmperf-main/` (`token_benchmark_ray.py`, `llm_correctness.py`). Root layout was curated by Girish Lade; the original toolkit is from the Ray Project.

## Features

- **Load test** (`token_benchmark_ray.py`) — spawns N concurrent requests and measures per-request and aggregate inter-token latency and generation throughput
- **Correctness test** (`llm_correctness.py`) — checks whether the API's outputs are correct under load
- **Result analysis notebook** (`analyze-token-benchmark-results.ipynb`) — visualize and compare benchmark runs
- **OpenAI-compatible APIs** — point it at any endpoint speaking the OpenAI API (vLLM, Anyscale, OpenAI, etc.)
- Consistent token counting via `LlamaTokenizer` regardless of the backend being tested

## Tech Stack

- Python (>=3.8, <3.11), Ray, Typer, LiteLLM, Transformers, Seaborn, Jupyter
- Build: setuptools (`pyproject.toml`)

## Quick Start

```bash
cd llmperf-main
pip install -e .

# Load test + correctness test
python token_benchmark_ray.py
python llm_correctness.py
```

Dev dependencies:

```bash
pip install -r requirements-dev.txt
```

## Project Structure

```
.
├── llmperf-main/
│   ├── token_benchmark_ray.py        # Ray-based load/throughput benchmark
│   ├── llm_correctness.py            # Correctness test
│   ├── src/llmperf/                 # Library code
│   ├── analyze-token-benchmark-results.ipynb  # Analysis notebook
│   ├── pyproject.toml               # Package metadata
│   └── requirements-dev.txt         # Dev dependencies
├── README.md
├── LICENSE.txt
└── NOTICE.txt
```

## Environment Variables

- `OPENAI_API_KEY` (or the key/endpoint variables for your provider) — needed by LiteLLM to talk to the target API

## License

See `LICENSE.txt` / `NOTICE.txt` (Apache 2.0, Ray Project).

---

Built by Girish Lade — https://ladestack.in
