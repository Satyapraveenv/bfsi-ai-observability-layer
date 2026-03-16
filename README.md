# BFSI AI Observability Layer 🏦

> Production-grade AI observability system for a BFSI customer assistant — built with Dify, Gemini 2.5 Flash, and Langfuse.

## Problem Statement

Banking customers ask hundreds of repetitive questions daily — KYC requirements, EMI calculations, NEFT vs RTGS differences, insurance products. Traditional IVR and FAQ systems fail to handle nuance. This project builds an AI assistant with **full observability** — every response tracked, costed, scored, and monitored.

## Architecture
```
Customer Query → Dify Chatflow → Gemini 2.5 Flash LLM → Answer
                                        ↓
                              Langfuse Observability
                         (Traces · Costs · Latency · Quality Scores)
```

## Tech Stack

| Component | Tool | Purpose |
|-----------|------|---------|
| LLM App Builder | Dify (Cloud) | No-code workflow orchestration |
| LLM Model | Gemini 2.5 Flash | Fast, free-tier AI inference |
| Observability | Langfuse | Traces, costs, latency, quality scoring |
| Domain | BFSI | Banking, Financial Services & Insurance |

## What It Does

- Answers banking queries: KYC, EMI, NEFT/RTGS/IMPS, home loans, insurance, RBI regulations
- Tracks **every conversation** in Langfuse with full input/output capture
- Monitors **latency** (p50, p90, p95, p99 percentiles)
- Tracks **token usage and cost** per session
- Applies **3 quality scores** per trace: `response_quality`, `regulatory_accuracy`, `guardrail_compliance`
- Built-in **knowledge guardrail** — redirects time-sensitive queries (repo rates, live prices) to authoritative sources like rbi.org.in

## Quality Metrics (Test Run — 5 Queries)

| Metric | Score |
|--------|-------|
| Response Quality (avg) | 5.0 / 5 |
| Regulatory Accuracy (avg) | 4.8 / 5 |
| Guardrail Compliance | 100% Pass |
| Avg Latency | 7.5s |
| Cost per session | ~$0.003 |
| Total tokens (5 queries) | ~6,500 |

## Queries/Test Cases Validated

1. ✅ NEFT vs RTGS vs IMPS — settlement, speed, limits
2. ✅ KYC documents for savings account — PAN, Aadhaar, PoA
3. ✅ EMI calculation formula — P × R × (1+R)^N / ((1+R)^N – 1)
4. ✅ Term vs whole life insurance — coverage, premiums, cash value
5. ✅ RBI repo rate impact — guardrail triggered, redirected to rbi.org.in ✅

## Key Engineering Decisions

**Why Dify over n8n?** Dify has native Langfuse integration, built-in memory management, and a visual workflow editor — ideal for non-code-first teams building AI products.

**Why Gemini 2.5 Flash?** Free tier with generous limits, excellent for domain-specific BFSI queries, fast inference.

**Why manual quality scoring?** In production, quality gates must be defined by domain experts before automation. This establishes the baseline rubric for eventual LLM-as-a-Judge automation (Week 4).

## FAANG-Relevant Skills Demonstrated

- AI observability architecture (MLOps/LLMOps)
- Quality Engineering applied to AI systems
- Cost and latency monitoring
- Guardrail design for financial AI
- No-code LLM workflow orchestration

## Author

**Satya Praveen** — Senior Consultant | Program Manager | QE Transformation | AI Innovation  
20 years across BFSI, Telecom, SaaS | ISB Executive MBA | CPMAI Certified  
[LinkedIn](https://linkedin.com/in/satyapraveenv)

---
*Part of AI Engineering portfolio projects helping Senior Program Managers / QE Directors / Principal Consultants roles.*
