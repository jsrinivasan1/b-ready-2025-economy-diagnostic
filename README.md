# B-READY 2025 Economy Diagnostic Generator

An interactive tool that generates detailed narrative diagnostics for any of the **101 economies** in the World Bank B-READY 2025 dataset. Select an economy, click Generate, and get a publication-ready report covering all 10 topics, 3 pillars each, with subcategory-level findings, peer benchmarks, and data-driven reform priorities.

> **[Launch Generator →](https://jsrinivasan1.github.io/B-READY-2025-Diagnostic-Generator/)**

---

## What It Produces

Each diagnostic is a structured narrative report with four sections:

### Section 1: Executive Summary
- Aggregate Pillar 1/2/3 scores with rank and percentile
- Comparison to global, regional, and income-group averages
- Identification of strongest and weakest pillars and topics
- Systemic patterns (e.g., "Pillar 2 is the weakest pillar in 8 of 10 topics")
- Benchmark table: economy vs. region vs. income group vs. global

### Section 2: Topic-Level Overview
- Summary table with all 10 topics showing Overall, P1, P2, P3, rank, and percentile
- Color-coded rows (green for top-performing topics, red for weakest)

### Section 3: Detailed Topic Analysis (10 topics × 3 pillars = 30 pillar narratives)
Each of the 10 topics gets:
- **Opening paragraph** — overall score, global/regional comparison, pillar balance assessment
- **Pillar 1: Regulatory Framework** — walks through each category and its subcategories, identifying where the economy scores well and where gaps exist (including specific zero-score subcategories by name)
- **Pillar 2: Public Services** — highlights digitalization gaps, interoperability weaknesses, and transparency deficits at the subcategory level
- **Pillar 3: Operational Efficiency** — describes time/cost/practice barriers with subcategory-level detail

### Section 4: Reform Priorities
- **5 data-driven priorities** automatically identified per economy using a composite urgency scoring algorithm
- Each priority gets a full paragraph: the score, gap to benchmarks, specific zero-score areas named, and prescriptive reform language calibrated to pillar type and score level
- **Cross-cutting observation** identifying systemic patterns (e.g., government-wide digital transformation needs)
- **Context note** for high-performing economies acknowledging that priorities are relative

---

## How the Priority Algorithm Works

Every topic-pillar combination (30 per economy) is scored on reform urgency using:

| Signal | Weight |
|--------|--------|
| Gap vs. global average | 1.0× |
| Gap vs. income-group average | 0.8× |
| Zero-score categories | 8 points each |
| Zero-score subcategories | 1.5 points each |
| Is the weakest pillar for this topic | +5 bonus |
| Absolute score below 20 | +15 bonus |
| Absolute score below 40 | +8 bonus |

The top 5 candidates are selected (one per topic, sorted by urgency). This ensures every economy — from the lowest-scoring to the highest — gets meaningful, differentiated priorities rather than hitting hard-coded thresholds that fail for well-performing economies.

---

## Usage

### Option 1: Open directly
Download `index.html` and open in any modern browser. Select an economy from the dropdown, click **Generate Diagnostic**, and the report renders instantly.

### Option 2: GitHub Pages
Deploy to GitHub Pages and share the link with your team.

### Option 3: Print / Save as PDF
Click **Print / Save PDF** in the toolbar. The browser print dialog opens with the toolbar hidden and page breaks at section headings. Save as PDF for distribution.

---

## Data

All data is embedded in the HTML file — no server, API, or external files needed.

**Source:** [World Bank B-READY 2025](https://www.worldbank.org/en/businessready) (December 2025)

Embedded datasets:
- **Economy scores** — 101 economies × 10 topics × (overall + P1 + P2 + P3 + category scores + subcategory scores)
- **Schema** — category/subcategory hierarchy and names for all 10 topics (~80 categories, ~227 subcategories)
- **Benchmarks** — precomputed averages by region (7 groups), income group (4 groups), and global
- **Ranks** — precomputed rank and percentile for every economy on every topic and pillar

---

## Technical Notes

- Single HTML file (~285 KB) with all data, styles, and logic embedded
- Zero runtime dependencies beyond Google Fonts (cosmetic only — works without)
- All narrative text is generated client-side from the data — no AI/LLM calls at runtime
- Consistent format guaranteed: every economy gets the same 4-section structure with the same pillar-by-pillar treatment for all 10 topics
- Print CSS hides toolbar, forces page breaks at section headings, and preserves table styling

---

## Companion Tool

This generator pairs with the **[B-READY 2025 Data Explorer](https://jsrinivasan1.github.io/B-READY-2025-Data-Explorer/)** dashboard, which provides interactive data exploration, economy comparisons, rankings, and scatter plot analysis across the same dataset. The Explorer is for slicing data; the Generator is for producing readable narrative documents.

---

## License

The underlying data is published by the World Bank under its [open data terms](https://www.worldbank.org/en/about/legal/terms-of-use-for-datasets). This tool is provided as-is for research and educational use.

---

## Citation

World Bank. 2025. *Business Ready 2025.* Washington, DC: World Bank.
