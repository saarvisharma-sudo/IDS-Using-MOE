# Dynamic Mixture-of-Experts (MoE) Model for Adaptive Multi-Class Intrusion Detection

A Mixture-of-Experts architecture for network intrusion detection that routes traffic to specialized "expert" sub-models per attack category, rather than relying on a single monolithic classifier.

## Overview

Conventional IDS models trade off detection accuracy across attack types — tuning for one category (e.g. DoS anomalies) typically degrades sensitivity to structurally different attacks (e.g. SQL injection). This project trains lightweight, specialized experts per attack class/cluster and uses a learned gating network to route each sample to the appropriate expert(s), aiming to retain per-class accuracy while avoiding the cost of 18 independent monolithic classifiers.

**Dataset:** [HybRID-18](https://doi.org/10.1007/s12046-025-02927-3) — a hybrid real + emulated network traffic dataset covering 18 attack types across 6 categories (malware, phishing/social engineering, network-based, injection, zero-day, credential-based), with 84 engineered flow-based features.

## Project Status

🚧 Active development — major project, academic year 2026–27.

## Team

| Name | Role |
|---|---|
| Saarvi Sharma | Contributor |
| Anshika Bharti | Contributor |
| Vaibhav Goswami | Contributor |

**Supervisor:** Mr. Aayush Sharma, Assistant Professor (Grade-1)

Department of Computer Science & Engineering and Information Technology, Jaypee University of Information Technology (JUIT), Waknaghat.

## Architecture

- **Specialized experts** — one per attack class or cluster of related classes (e.g. SQLi, XSS, phishing/URL, credential-based, network-based, malware-based)
- **Gating network** — dynamically routes/weights experts per input sample
- **Fusion layer** — combines expert outputs into the final classification

## Getting Started

```bash
git clone https://github.com/saarvisharma-sudo/IDS-using-MOE.git
cd IDS-using-MOE
pip install -r requirements.txt
```

> Fill in exact setup steps (data download/preprocessing, training command, evaluation command) once the codebase structure is pushed.

## Repository Structure

```
.
├── data/           # dataset download/preprocessing scripts (raw data not committed)
├── src/            # model, gating network, expert definitions, training/eval code
├── notebooks/       # exploratory analysis, result visualization
├── docs/           # literature review, dataset notes, design docs
├── tests/          # unit tests
├── requirements.txt
├── LICENSE
└── CONTRIBUTING.md
```

> Adjust this tree to match your actual local layout before pushing.

## Contributing

Contributions are welcome via fork + pull request — see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Citation

If you use this work, please cite the HybRID-18 dataset paper:

> Rani, S., Kumar, S. (2025). HybRID-18: a realistic and feature-rich intrusion detection dataset for machine learning benchmarking. *Sådhanå*, 50, 272.

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
