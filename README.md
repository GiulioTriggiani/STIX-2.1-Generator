<div align="center">

# STIX 2.1 Generator

**Automatic Generation of STIX 2.1 Bundles from Threat Intelligence Reports using Large Language Models**

[![Thesis](https://img.shields.io/badge/Type-Master's%20Thesis-blue)](thesis/)
[![Python](https://img.shields.io/badge/Python-3.9+-green)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)
[![TI Mindmap HUB](https://img.shields.io/badge/Integrated-TI%20Mindmap%20HUB-purple)](https://ti-mindmap-hub.com)

[Paper (PDF)](thesis/Tesi_Triggiani_Giulio.pdf) · [TI Mindmap HUB](https://ti-mindmap-hub.com) · [Research Repository](https://github.com/TI-Mindmap-HUB-Org/ti-mindmap-hub-research)

</div>

---

## Overview

This repository contains the code, datasets, and evaluation results from my Master's thesis on **automatic STIX 2.1 bundle generation using Generative AI**. The research explores how Large Language Models (LLMs) can transform unstructured threat intelligence reports into structured, machine-readable STIX 2.1 bundles.

The methodology developed in this thesis has been **integrated into [TI Mindmap HUB](https://ti-mindmap-hub.com)**, a research platform exploring GenAI applications in Cyber Threat Intelligence.

### Academic Context

| | |
|---|---|
| **Thesis Title** | Automatic Generation of STIX 2.1 Bundles using Large Language Models |
| **Author** | Giulio Triggiani |
| **University** | University of Salerno (UNISA) |
| **Degree** | Master's in Computer Science / Cybersecurity |
| **Supervisors** | Assoc. Prof. Arcangelo Castiglione, Ing. Antonio Formato |
| **Year** | 2024/2025 |

---

## Research Objectives

1. **Automate STIX generation** — Convert unstructured threat reports into STIX 2.1 bundles
2. **Evaluate LLM accuracy** — Measure precision and recall of object extraction
3. **Compare approaches** — Standard vs. Graph-based generation methods
4. **Validate output quality** — Ensure STIX schema compliance and semantic correctness

---

## Repository Structure

```
STIX-2.1-Generator/
├── README.md                     # This file
├── LICENSE                       # MIT License
├── CITATION.cff                  # Citation metadata
├── thesis/
│   └── Tesi_Triggiani_Giulio.pdf # Full thesis document
├── notebooks/
│   ├── GenAI_STIX_2_1_Generator_V13.ipynb           # Main generator
│   ├── Evaluation_GenAI_STIX_2_1_Generator_V9_Chart.ipynb  # Standard evaluation
│   └── Graph_Evaluation_GenAI_STIX_2_1_Generator_V6.ipynb  # Graph evaluation
├── dataset/                      # Test datasets
└── results/
    ├── standard/                 # Standard evaluation results
    └── graph/                    # Graph-based evaluation results
```

---

## Methodology

### STIX 2.1 Generation Pipeline

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Threat Report  │────▶│   LLM Analysis  │────▶│  STIX Objects   │
│  (Unstructured) │     │   (GPT-4)       │     │  (Structured)   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                │
                                ▼
                        ┌─────────────────┐
                        │   Validation    │
                        │  & Bundling     │
                        └─────────────────┘
```

### Objects Generated

The system extracts and generates:

**STIX Domain Objects (SDOs)**
- Threat Actor
- Malware
- Campaign
- Attack Pattern (MITRE ATT&CK)
- Indicator
- Identity
- Report

**STIX Cyber Observables (SCOs)**
- IPv4/IPv6 Address
- Domain Name
- URL
- File (with hashes)
- Email Address

**STIX Relationship Objects (SROs)**
- Relationships between all objects
- Semantic connections (uses, indicates, targets, etc.)

### Evaluation Approaches

Two evaluation methodologies were developed:

| Approach | Description | Metrics |
|----------|-------------|---------|
| **Standard** | Object-by-object comparison | Precision, Recall, F1-Score |
| **Graph-based** | Structural similarity of bundles | Graph Edit Distance, Jaccard Similarity |

---

## Results Summary

Key findings from the evaluation:

| Metric | Standard Approach | Graph Approach |
|--------|-------------------|----------------|
| SDO Precision | ~85% | ~82% |
| SDO Recall | ~78% | ~75% |
| Relationship Accuracy | ~72% | ~70% |
| Schema Compliance | 100% | 100% |

*See the thesis document for complete evaluation results and analysis.*

---

## Integration with TI Mindmap HUB

The STIX generation methodology developed in this thesis has been integrated into **[TI Mindmap HUB](https://ti-mindmap-hub.com)**, where it processes ~40 threat intelligence reports weekly.

### Production Implementation

- Automated STIX bundle generation for all processed articles
- Real-time validation against STIX 2.1 schema
- Export capability for SIEM/SOAR/TIP integration
- Public API access via MCP server

### Related Resources

- **Platform**: [ti-mindmap-hub.com](https://ti-mindmap-hub.com)
- **Research Repository**: [TI-Mindmap-HUB-Org/ti-mindmap-hub-research](https://github.com/TI-Mindmap-HUB-Org/ti-mindmap-hub-research)
- **STIX Documentation**: [STIX-GENERATION.md](https://github.com/TI-Mindmap-HUB-Org/ti-mindmap-hub-research/blob/main/documentation/STIX-GENERATION.md)

---

## Getting Started

### Prerequisites

- Python 3.9+
- Jupyter Notebook
- Azure OpenAI API access (or OpenAI API)

### Installation

```bash
# Clone the repository
git clone https://github.com/GiulioTriggiani/STIX-2.1-Generator.git
cd STIX-2.1-Generator

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Configuration

Create a `.env` file with your API credentials:

```env
AZURE_OPENAI_ENDPOINT=https://your-endpoint.openai.azure.com/
AZURE_OPENAI_API_KEY=your-api-key
AZURE_OPENAI_DEPLOYMENT=gpt-4
```

### Usage

1. Open the main notebook:
   ```bash
   jupyter notebook notebooks/GenAI_STIX_2_1_Generator_V13.ipynb
   ```

2. Provide a threat intelligence report URL or text

3. Run all cells to generate the STIX bundle

4. Export the bundle as JSON for use in your security tools

---

## Citation

If you use this work in your research, please cite:

```bibtex
@mastersthesis{triggiani2025stix,
  title = {Automatic Generation of STIX 2.1 Bundles using Large Language Models},
  author = {Triggiani, Giulio},
  year = {2025},
  school = {University of Salerno},
  type = {Master's Thesis},
  supervisor = {Castiglione, Arcangelo and Formato, Antonio},
  url = {https://github.com/GiulioTriggiani/STIX-2.1-Generator}
}
```

Or cite the TI Mindmap HUB platform:

```bibtex
@misc{timindmaphub2025,
  title = {TI Mindmap HUB: An Experimental Platform for GenAI-Powered Cyber Threat Intelligence},
  author = {TI Mindmap HUB},
  year = {2025},
  url = {https://ti-mindmap-hub.com}
}
```

---

## References

- [STIX 2.1 Specification (OASIS)](https://docs.oasis-open.org/cti/stix/v2.1/stix-v2.1.html)
- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [stix2 Python Library](https://github.com/oasis-open/cti-python-stix2)
- [TI Mindmap HUB Research](https://github.com/TI-Mindmap-HUB-Org/ti-mindmap-hub-research)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- **Assoc. Prof. Arcangelo Castiglione** — Academic supervisor, University of Salerno
- **Ing. Antonio Formato** — Industry supervisor and TI Mindmap HUB creator
- **University of Salerno (UNISA)** — Academic institution
- **TI Mindmap HUB** — Platform integration and production deployment
- **OASIS CTI TC** — STIX 2.1 standard development

---

<div align="center">

**Part of the [TI Mindmap HUB](https://ti-mindmap-hub.com) Research Initiative**

</div>
