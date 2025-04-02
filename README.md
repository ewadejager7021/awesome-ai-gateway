# Awesome AI Gateway [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![GitHub stars](https://img.shields.io/github/stars/cuihuan/awesome-ai-gateway?style=social)](https://github.com/cuihuan/awesome-ai-gateway/stargazers)
[![Evaluation set](https://img.shields.io/badge/📊-evaluation%20set-orange)](BENCHMARKS.md)
[![Data verified](https://img.shields.io/github/last-commit/cuihuan/awesome-ai-gateway?label=data%20verified&color=success&logo=githubactions&logoColor=white)](.github/workflows/daily-update.yml) [![CI](https://img.shields.io/github/actions/workflow/status/cuihuan/awesome-ai-gateway/ci.yml?label=259%20tests)](https://github.com/cuihuan/awesome-ai-gateway/actions/workflows/ci.yml)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md) [![License: CC0](https://img.shields.io/badge/license-CC0-lightgrey.svg)](LICENSE)

> **Pick one in ~10 seconds, understand why, and check every number yourself.** A decision tree over 180+ gateways, a handbook that explains how they actually work (and fail), and a reproducible cost benchmark plus dated evidence behind every claim — including what we exclude and why. CC0, no vendor money, no affiliate links.

💸 _Built the hard way: **I burned $788 on AI coding in a single day** — one flagship model ate 78% of it, just because I'd defaulted everything to the priciest option. So I mapped the whole gateway landscape. → full story in **Why this exists** below · [the full comparison](compare/coding-agent-routers-2026.md#the-three-mechanism-tiers)_

**Languages:** English · [简体中文](README.zh-CN.md)

<p align="center">
<a href="#which-gateway-should-i-use"><kbd> &nbsp; 🧭 Pick one &nbsp; </kbd></a> &nbsp;
<a href="LANDSCAPE.md"><kbd> &nbsp; 🌍 State of the space &nbsp; </kbd></a> &nbsp;
<a href="#-learn-how-ai-gateways-work"><kbd> &nbsp; 📖 Learn how they work &nbsp; </kbd></a> &nbsp;
<a href="BENCHMARKS.md"><kbd> &nbsp; 📊 Verify the numbers &nbsp; </kbd></a> &nbsp;
<a href="https://cuihuan.github.io/awesome-ai-gateway/"><kbd> &nbsp; 🚀 Live site &nbsp; </kbd></a>
</p>

<p align="center">
  <a href="#the-requirements-map"><img src="assets/hero-demo.gif" alt="How this list works, in four steps: pick by requirement (routing, cost, observability, compliance, supply-chain, caching, K8s, MCP/agents, fidelity), match the trust tier to your data, check evidence-based five-axis scores, and mind the 106x model cost spread ($0.03 vs $3.01 for the same 100K-token report)." width="840"></a>
</p>

## Contents

- [Which gateway should I use](#which-gateway-should-i-use)
  - [✅ Why trust this list](#-why-trust-this-list)
- [🌍 State of the landscape (2026)](#-state-of-the-landscape-2026)
- [⚡ 10-second answers](#-10-second-answers)
- [📖 Learn: how AI gateways work](#-learn-how-ai-gateways-work)
- [🔥 Top gateways (by stars)](#-top-gateways-by-stars)
  - [🩺 Maintenance signal — what the star count hides](#-maintenance-signal--what-the-star-count-hides)
- [💰 Cost-first: cheapest multi-model access](#-cost-first-cheapest-multi-model-access)
  - [🆓 Free tiers that still work — the verified-limits table](#-free-tiers-that-still-work--the-verified-limits-table)
- [🔓 Self-hosted open source](#-self-hosted-open-source)
- [🏢 Enterprise & compliance](#-enterprise--compliance)
- [🌐 First-party gateways (cloud & model vendors)](#-first-party-gateways-cloud--model-vendors)
- [🇨🇳 China ecosystem](#-china-ecosystem)
- [🤖 MCP & agent gateways](#-mcp--agent-gateways)
- [🔧 More by capability (cross-cutting)](#-more-by-capability-cross-cutting)
  - [🧠 Smart routing & model selection](#-smart-routing--model-selection)
  - [💾 Prompt caching through a gateway — the money question](#-prompt-caching-through-a-gateway--the-money-question)
  - [📊 Observability & cost tracking](#-observability--cost-tracking)
  - [🚢 Kubernetes-native & inference infra](#-kubernetes-native--inference-infra)
- [Quick comparison](#quick-comparison)
- [The requirements map](#the-requirements-map)
- [How to choose safely](#how-to-choose-safely)
  - [🔒 Who sees your prompts? — the data-retention matrix](#-who-sees-your-prompts--the-data-retention-matrix)
  - [🔐 Supply-chain security — who signs their releases, and what actually got hacked](#-supply-chain-security--who-signs-their-releases-and-what-actually-got-hacked)
  - [🧰 Companion tools — verify what you picked](#-companion-tools--verify-what-you-picked)
  - [Community relay watch-list](#community-relay-watch-list)
- [📊 Latest evaluations](#-latest-evaluations)
- [📰 What's new](#-whats-new)
- [🚀 Recent releases (auto-updated)](#-recent-releases-auto-updated)
- [📚 Essential reading](#-essential-reading)
- [Guides & comparisons](#guides--comparisons)
- [FAQ](#faq)
- [Glossary](#glossary)
- [Why this exists](#why-this-exists)
- [Who maintains this — and the conflict of interest](#who-maintains-this--and-the-conflict-of-interest)
- [🔌 Use the data — it's an API](#-use-the-data--its-an-api)
- [🔗 Related lists](#-related-lists)
- [Star history](#star-history)

## Which gateway should I use

<p align="center">
  <img src="assets/decision-tree.png" alt="Decision tree: which AI gateway should you use? Hosted (OpenRouter, Vercel, Cloudflare, Bedrock, Azure, Vertex, Portkey) vs self-hosted open source (LiteLLM, Bifrost, new-api, one-api, GPT-Load, Kong, Higress, APISIX, Envoy AI Gateway, agentgateway), chosen by what you need." width="840">
</p>

**⚡ Fast answer** — one sane default per need (alternatives in each linked section):

| I need…                                               | Start with                                                                                                                               | Drill into                                                                                                    |
| ----------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Cheapest access to many models, zero ops              | **Vercel / Cloudflare** (0% markup, your keys) · **OpenRouter** (~5.5% fee, one balance)                                                 | Cost-first                                                                                                    |
| Zero markup on my own keys                            | **Vercel** / **Cloudflare**                                                                                                              | Cost-first                                                                                                    |
| Self-host, broadest features                          | **LiteLLM**                                                                                                                              | Self-hosted                                                                                                   |
| Self-host, lowest overhead                            | **Bifrost** (Go)                                                                                                                         | Self-hosted                                                                                                   |
| Route Claude Code / Codex to another model            | **LiteLLM** / **Bifrost** (both measured 3/3)                                                                                            | Smart routing                                                                                                 |
| Cut my Claude Code / Cursor bill — without a ban      | **claude-code-router** (BYO-key, zero ban reports)                                                                                       | [Coding-agent routers compared](compare/coding-agent-routers-2026.md#where-each-tool-sits--from-its-own-docs) |
| Cut token spend without changing model or provider    | **headroom** (compression proxy — attacks context size, not price)                                                                       | Self-hosted                                                                                                   |
| China models + team key billing                       | **new-api**                                                                                                                              | China ecosystem                                                                                               |
| Enterprise K8s + audit                                | **Kong** / **Higress** — audit logs are paid/hosted-tier on both ([tiers](BENCHMARKS.md#part-7--identity--governance-the-sso-tax-table)) | Enterprise                                                                                                    |
| Strongest compliance (HIPAA/FedRAMP)                  | **Azure** / **Bedrock**                                                                                                                  | First-party                                                                                                   |
| Sensitive prompts — who sees / logs / trains on them? | **Self-host** or **ZDR-default** (Vercel / Requesty)                                                                                     | Who sees your prompts                                                                                         |
| Govern agents / MCP traffic                           | **agentgateway**                                                                                                                         | MCP & agents                                                                                                  |

<details>
<summary>📋 The full decision tree — every branch, copy-pasteable</summary>

```text
Do you want to self-host?
│
├─ NO — hosted, minimal ops
│   ├─ Cheapest access to many models ──────────▶ OpenRouter · Vercel AI Gateway (0% markup)
│   ├─ Free control plane over your own keys ───▶ Cloudflare AI Gateway
│   ├─ EU data residency matters ───────────────▶ Requesty · Eden AI · nexos.ai
│   └─ Already on one cloud ────────────────────▶ AWS Bedrock · Azure APIM · Vertex AI
│
└─ YES — self-hosted / open source
    ├─ Python stack, broadest features ─────────▶ LiteLLM
    ├─ Raw performance (Go/Rust/TS) ────────────▶ Bifrost (0.62 ms measured) · Portkey Gateway (2.65 ms; fidelity 1/3)
    ├─ Built-in evals + observability ──────────▶ LiteLLM · Bifrost · Helicone (maintenance mode)
    ├─ Multi-user keys + budgets + admin UI ────▶ LiteLLM · new-api   (family / small team)
    ├─ CN models + CNY billing ─────────────────▶ new-api · one-api · GPT-Load
    ├─ Enterprise K8s, audit, guardrails ───────▶ Kong · Higress · APISIX · Envoy AI Gateway
    └─ Governing AI agents & MCP traffic ───────▶ agentgateway · Lunar.dev
```

</details>

### ✅ Why trust this list
- ✅ **Independent — no vendor money, no affiliate links, CC0.** Unlike affiliate-driven relay "rankings," nobody pays to appear here.
- ✅ **Reproducible, not asserted.** Every cost cell is computed from [open pricing data](data/models.json) by a [unit-tested script](scripts/cost_calc.py); stars refresh daily via CI.
- ✅ **Honest about risk.** We disclose CVEs, label archived/stale projects, and exclude gray-market relays — with the research to back it.

---

> **Why this matters:** the same task can cost **100× more** depending on the model behind your gateway. An **AI gateway** sits between your code and LLM providers — one endpoint, one key, many models — handling routing, failover, caching, rate limits, cost tracking and guardrails, so you change a `base_url` instead of rewriting your app. Pick the gateway here, then the [evaluation set](BENCHMARKS.md#part-1--authoritative-model-benchmarks) shows which model to route to.

<p align="center">
  <a href="BENCHMARKS.md"><img src="assets/cost-spread.png" alt="Cost to write one 100K-token report: $0.03 on DeepSeek vs $3.01 on GPT-5.5 — a 106x spread, computed by a unit-tested script" width="760"></a>
</p>

⭐ **Found this useful? [Star it](https://github.com/cuihuan/awesome-ai-gateway)** — that's how the next engineer choosing a gateway finds it. CC0, no signup, no tracking, no vendor money.

## 🌍 State of the landscape (2026)

The standalone AI gateway is being squeezed from both ends. Underneath, hyperscalers now ship routing and spend caps natively; above, the coding-agent wave produced a faster-growing class of gateway that most round-ups miss. The part that consolidated is the independent middle — a company whose entire product was the gateway.

| 2026                                                                    | What happened                                                                  | State                                                                        |
| ----------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| TensorZero <!--s:tensorzero/tensorzero-->⭐ 11.7k<!--/s-->               | VC-backed OSS gateway archived its repo (Jun 11)                               | Read-only; Apache-2.0 code and forks live on                                 |
| Pydantic AI Gateway <!--s:pydantic/pydantic-ai-gateway-->⭐ 193<!--/s--> | Archived (Mar 30), folded into Logfire                                         | The gateway became a platform feature                                        |
| Helicone <!--s:Helicone/helicone-->⭐ 6.2k<!--/s-->                      | Acquired by Mintlify (Mar)                                                     | Still committing — roadmap risk, not liveness                                |
| Portkey                                                                 | Acquired by Palo Alto Networks (closed May 29)                                 | Now a security platform's control plane                                      |
| OpenRouter                                                              | **Stripe agreed to acquire** (announced Aug 19); terms undisclosed, press >$7B | Agreed, not yet confirmed closed — OpenRouter promises no product/API change |
| BricksLLM, Glide                                                        | No commits since 2025-01 / 2024-08                                             | Never archived; the failure mode is silence                                  |

Not a collapse — the same year, LiteLLM <!--s:BerriAI/litellm-->⭐ 61.2k<!--/s--> kept compounding, Bifrost <!--s:maximhq/bifrost-->⭐ 8.8k<!--/s--> won on measured overhead, Envoy AI Gateway reached v1.0 (Jun 23) as the first CNCF-backed production-stable option, and the coding-agent tier plus token-compression proxies became the fastest-growing categories in this list.

**Three things that changes for you:** check the last commit before the feature matrix; prefer code you can keep over a control plane you cannot; and if your traffic already lives in one cloud, that cloud's native gateway is now a real answer.

📉 **The full picture — the consolidation evidence, the six-check evaluation standard, and three dated predictions with their disproof conditions: [LANDSCAPE.md](LANDSCAPE.md)**

## ⚡ 10-second answers

The questions people actually ask (sourced from real threads) — answered first:

| You're asking…                                               | The answer                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "Cheapest way to hit many models right now?"                 | **OpenRouter** (~5.5% credit fee, <!--omc-->~340<!--/omc--> models) — or **0% markup on your own keys**: Vercel / Cloudflare AI Gateway → Cost-first                                                                                                                                                                                                                                   |
| "Which free tiers still work, and what are the real limits?" | OpenRouter `:free`: **50 req/day** (<$10 credits) or **1,000/day** ($10+ top-up), 20 req/min shared ([official limits](https://openrouter.ai/docs/api-reference/limits)). Eleven providers verified row-by-row in the free-tier table. The catch with "free": your prompts may train someone's model — check the fine print                                                            |
| "How much does the _model_ choice matter?"                   | **106×** — the same 100K-token report costs $0.03 (DeepSeek) vs $3.01 (GPT-5.5) → [computed tables](BENCHMARKS.md#part-3--real-world-token-cost-computed) · [calculator](https://cuihuan.github.io/awesome-ai-gateway/cost-calculator.html)                                                                                                                                            |
| "How much latency does the gateway itself add?"              | **Independently measured** (nobody else does): Bifrost **0.62 ms** · Portkey OSS **2.65 ms** · LiteLLM **5.83 ms** per request → [data](https://github.com/cuihuan/llm-gateway-bench/blob/main/data/overhead.json)                                                                                                                                                                     |
| "Will my prompt-cache discount still work through it?"       | **Often no — and it's silent.** The most under-claimed discount in most bills → caching through a gateway                                                                                                                                                                                                                                                                              |
| "Who sees my prompts?"                                       | The gateway does, always — and routers range from **ZDR-by-default** to **training on your prompts by ToS**. See the data-retention matrix                                                                                                                                                                                                                                             |
| "Sick of LiteLLM — what else?"                               | LiteLLM alternatives, compared honestly (overhead-measured: it's 10× heavier than Bifrost)                                                                                                                                                                                                                                                                                             |
| "Will it break my Claude Code / Codex / Cursor?"             | **The #1 gateway failure — but we measured it.** Routing Claude Code to an OpenAI model, **LiteLLM & Bifrost translate cleanly (3/3); Portkey OSS doesn't offer the path** → [the independent test](https://cuihuan.github.io/llm-gateway-bench/article.html?slug=does-your-gateway-break-claude-code). Still run _your_ agent (tools + streaming) through it, and **pin the version** |

## 📖 Learn: how AI gateways work

_The list tells you **which** gateway;