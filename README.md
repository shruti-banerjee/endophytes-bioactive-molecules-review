# Endophyte Bioactive Compounds — Computational Analysis

A bioinformatics project bridging microbiology and data science to computationally analyse bioactive secondary metabolites produced by endophytic microorganisms.

Inspired by a literature review on *Endophytes as a Treasure Trove of Bioactive Molecules* (Amity University, 2019), this project applies cheminformatics and data analysis to evaluate endophyte-derived compounds as potential drug candidates.

---

## Background

Endophytes are microorganisms (fungi, bacteria) that live asymptomatically inside plant tissues. They produce a remarkable diversity of bioactive secondary metabolites — many of which have become foundational drugs:

- **Taxol (Paclitaxel)** — from *Taxomyces andreanae*, now a frontline anticancer drug
- **Camptothecin** — from *Fusarium solani*, precursor to topotecan and irinotecan
- **Podophyllotoxin** — precursor to etoposide and teniposide

This project asks: *which of these compounds have the best drug-like properties, and what does the research landscape look like computationally?*

---

## Project Structure

```
endophyte-bioactives-analysis/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── compounds.csv              # curated compound dataset
│
├── notebooks/
│   ├── 01_data_curation.ipynb     # build dataset + PubChem API fetch
│   ├── 02_lipinski_filter.ipynb   # drug-likeness analysis with RDKit
│   ├── 03_pubmed_trends.ipynb     # publication trend analysis via NCBI
│   └── 04_bioactivity_heatmap.R   # bioactivity heatmap in R/ggplot2
│
└── figures/
    ├── lipinski_radar.png
    ├── bioactivity_heatmap.png
    └── pubmed_trends.png
```

---

## Modules

### Module 1 — Data Curation (`01_data_curation.ipynb`)
- Curates 15+ endophyte-derived bioactive compounds from literature
- Fetches molecular weight, formula, SMILES, and InChIKey from **PubChem API**
- Saves structured dataset to `data/compounds.csv`

### Module 2 — Drug-likeness Analysis (`02_lipinski_filter.ipynb`)
- Computes Lipinski's Rule of Five descriptors using **RDKit**
  - Molecular weight, LogP, H-bond donors, H-bond acceptors
- Flags compounds passing/failing oral drug-likeness criteria
- Visualises results as a radar/scatter plot

### Module 3 — PubMed Trend Analysis (`03_pubmed_trends.ipynb`)
- Queries **NCBI E-utilities (Biopython Entrez)** for annual publication counts
- Search terms: `endophyte + anticancer`, `endophyte + antimicrobial`, `endophyte + antifungal`
- Plots research growth from 2000–2024

### Module 4 — Bioactivity Heatmap (`04_bioactivity_heatmap.R`)
- Cross-tabulates compounds vs. bioactivity categories
- Plots binary heatmap using **ggplot2 / pheatmap**

---

## Setup

```bash
git clone https://github.com/shrutibanerjee/endophyte-bioactives-analysis.git
cd endophyte-bioactives-analysis
pip install -r requirements.txt
```

For the R notebook, open in RStudio and install packages as prompted.

---

## Key Findings

*(To be updated as analysis is completed)*

- X out of 15 compounds pass Lipinski's Rule of Five
- Publication count for endophyte research grew X% from 2000 to 2024
- Anticancer activity is the most represented bioactivity class

---

## Skills Demonstrated

`Python` `R` `RDKit` `Biopython` `PubChem API` `NCBI E-utilities` `pandas` `ggplot2` `cheminformatics` `data visualisation` `literature mining`

---

## References

1. Strobel & Daisy (2003). Bioprospecting for microbial endophytes. *Microbiology and Molecular Biology Reviews*, 67(4), 491–502.
2. Tan & Zou (2001). Endophytes: a rich source of functional metabolites. *Natural Product Reports*, 18.
3. Wani et al. (1971). The isolation and structure of taxol. *Journal of the American Chemical Society*, 93(9).

---

*Author: Shruti Banerjee | MSc Bioinformatics, Pondicherry University*
