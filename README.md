# Parametric Stubbornness: Mechanistically Isolating the Layer Shift and Sparsity Gradient of RAG Knowledge Conflicts in Llama-3

[![arXiv](https://img.shields.io/badge/arXiv-Coming%20Soon-b31b1b.svg)](https://arxiv.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **Author:** Houman Rajabi (Department of Computer Science, University of Turin)

---

### 🚀 Status: Codebase & Dataset Preparation
*This repository currently serves as a placeholder for the upcoming arXiv preprint and ACL SRW submission.* We are finalizing the code cleanups to ensure full reproducibility. The complete mechanistic tracing codebase, calibrated Direct Logit Attribution (DLA) scripts, and the lexically filtered minimal-pair dataset will be pushed to this repository shortly. 

Please **Watch** or **Star** this repository to be notified when the code and data are officially released.

---

## Abstract
Retrieval-Augmented Generation (RAG) often introduces knowledge conflicts where context contradicts a Large Language Model's (LLM) parametric memory. While models behaviorally default to provided context, the mechanistic routing of this "tug-of-war" remains largely unexplored. Using Two-Phase Activation Patching and inference-time interventions on Meta-Llama-3-8B across 452 minimal-pair conflicts, we vary contextual explicitness to uncover three phenomena:

1. **The Sparsity Gradient:** As context shifts from explicit to implicit, distributed copying circuits collapse into a sparse bottleneck of deep semantic routers. Ablating just two heads shifts the logit distribution toward the parametric truth in 74% of implicit (Partial-condition) records, yielding a mean Logit Difference (LD) recovery of +0.34.
2. **Parametric Stubbornness:** FFNs do not "forget" facts; they stubbornly retrieve them but are out-voted by contextual attention in the residual stream. Amplifying late-layer FFNs causally shifts the model toward the truth.
3. **Contextual Contamination:** In 52.4% of explicit conflicts, the contextual signal overwhelmingly contaminates FFN retrieval mechanisms. 

Ultimately, we demonstrate that RAG hallucinations are not monolithic errors, but dynamic, mechanistically steerable competitions.

---

## 🛠️ Planned Release Schedule

- [ ] **Minimal-Pair Dataset:** The lexically-filtered dataset of 452 RAG conflicts across Synthetic, Naturalistic, and Partial conditions. 
- [ ] **Two-Phase Causal Tracing Code:** Scripts to reproduce the coarse-to-fine activation patching (AIE) using the `TransformerLens` library.
- [ ] **Inference-Time Interventions:** Scripts to replicate the surgical suppression of sparse routing heads and the parametric amplification (Megaphone) experiments.

---

## Citation
If you find this work or the upcoming codebase useful in your research, please consider citing our preprint:

```bibtex
@misc{rajabi2026parametric,
      title={Parametric Stubbornness: Mechanistically Isolating the Layer Shift and Sparsity Gradient of RAG Knowledge Conflicts in Llama-3}, 
      author={Houman Rajabi},
      year={2026},
      eprint={XXXX.XXXXX},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
