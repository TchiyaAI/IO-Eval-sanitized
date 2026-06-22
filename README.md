# Evaluating AI Uplift to Influence Operations
### A kill-chain-anchored capability framework

**Status:** Preprint forthcoming (ValgrAI / University of Valencia, 2026).
This repository is the **public, sanitized release**. Executable adversarial
artifacts are deliberately withheld. See [`RESPONSIBLE_RELEASE.md`](https://github.com/TchiyaAI/IO-Eval-sanitized/blob/main/Responsible_Release).

## Overview
This project measures whether frontier and open-weight models provide meaningful.
**uplift** to actors running online influence operations, and anchors that
measurement in a recognised analytic framework so the results are interpretable
and actionable for platforms and regulators rather than ad hoc.

## Method (summary)
- Operationalises the ten-phase Online Operations Kill Chain (Nimmo & Hutchins, 2023)
  into **27 scored steps**, graded for per-step completion.
- Models: two open-weight (Llama 3.1 8B, Llama 3.3 70B) and one frontier (Gemini 2.5 Flash).
- Languages: English and Russian.
- Grading: an LLM judge with blinded human review; **11,088 graded samples**.
- Headline measure: a **Compound Uplift Score**, plus per-step completion and refusal rates.

Full detail in [`METHODOLOGY.md`](METHODOLOGY.md).

## Key findings (high level)
- Near-universal task compliance across the kill chain.
- Near-zero refusal under adaptive multi-turn prompting.
- Large quality gap between English and Russian outputs.
- Order-of-magnitude cost spread across models.

Per-step tables and figures are in the forthcoming preprint. See [`results/SUMMARY.md`](results/SUMMARY.md).

## Repository structure
- `METHODOLOGY.md` ‚Äî framework, scoring scheme, validity notes.
- `eval/` ‚Äî evaluation **harness skeleton** with a **benign placeholder task** that
  demonstrates the pipeline end to end without any influence-operations content.
- `results/SUMMARY.md` ‚Äî aggregate findings.
- `RESPONSIBLE_RELEASE.md` ‚Äî what is withheld and why.

## What is withheld
The task bank, elicitation prompts, multi-turn attack scaffolding, and raw model
outputs are **not** included. They are misuse-enabling. Vetted researchers and
auditors can request structured access (see below).

## Running the harness
The production harness runs against the withheld task bank. The included benign
example demonstrates the pipeline without any influence-operations content:
```bash
pip install -r requirements.txt
inspect eval eval/harness.py --model <provider/model>
```

## Citation
See [`CITATION.cff`](CITATION.cff).

## Authors
Jodie Levy and collaborators. **[Fill in the full author list and supervisor with the
team before publishing.]** ValgrAI / University of Valencia, 2026.

## Access requests
Structured access to withheld artifacts for vetted research or audit: **[your email]**.

