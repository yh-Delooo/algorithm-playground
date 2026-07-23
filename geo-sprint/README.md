# geo-sprint

> Survey of brand visibility patterns in AI search engines (千问 / 豆包 / DeepSeek).
> Goal: find "small brands" that rank unusually high, characterize their tactics.

---

## Status

🚧 **In progress** — not started yet. See "Roadmap" below.

## Why this project

- Practice **embedding + clustering + anomaly detection** on real data
- Build a public artifact that demonstrates end-to-end ML workflow
- Findings may inform a separate (non-BTN) commercial interest in GEO

> **Note**: this repo is personal/educational. No commercial client work, no employer data.

---

## Roadmap (3-week sprint)

Detailed checklist lives at:
`/Users/chan/Documents/BTN/2026-07-23_转行策略/A-GEO_Sprint执行清单.md`

### Week 1 — Setup + data collection
- [ ] Python environment (conda env: `geo-sprint`)
- [ ] Install: playwright, sentence-transformers, faiss, scikit-learn
- [ ] Keywords list (10 starting points)
- [ ] Smoke test: 1 platform, 2 keywords, 10 results each

### Week 2 — Embedding + clustering + anomaly
- [ ] Crawl 3 platforms × 10 keywords × 10 results = 300 records
- [ ] Embed all snippets with `BAAI/bge-large-zh-v1.5`
- [ ] KMeans clustering → which topics cluster together
- [ ] Isolation Forest → which brands rank anomalously high

### Week 3 — Report + automation
- [ ] Write GEO survey report (10-20 pages PDF)
- [ ] Visualize: cluster scatter + anomaly highlight
- [ ] Wrap pipeline as one-command script
- [ ] (Optional) share with relevant people

---

## Tech stack

| Layer | Tool |
|---|---|
| Crawling | Playwright (Chromium) |
| Embedding | `BAAI/bge-large-zh-v1.5` (or `text-embedding-3` if API budget allows) |
| Vector store | FAISS (in-memory) |
| Clustering | scikit-learn KMeans / DBSCAN |
| Anomaly detection | scikit-learn IsolationForest |
| Visualization | Plotly / Seaborn |
| Report | Jupyter + nbconvert / Quarto |
| Automation | Bash + cron (later) |

---

## Directory layout

```
geo-sprint/
├── README.md              ← you are here
├── data/
│   ├── raw/               ← crawler outputs (JSON, gitignored)
│   └── processed/         ← cleaned + embedded (parquet)
├── notebooks/
│   ├── 01-crawl.ipynb
│   ├── 02-embed-cluster.ipynb
│   └── 03-anomaly.ipynb
├── scripts/
│   ├── crawl.py
│   ├── embed.py
│   └── run_pipeline.sh
├── reports/
│   └── geo-survey-2026.pdf   ← final deliverable
└── assets/                  ← images for report
```

---

## Out of scope (deferred)

- ❌ Real-time monitoring pipeline (overkill for learning)
- ❌ Server / dashboard hosting (not needed yet)
- ❌ Multiple language models comparison (do later)

---

## References

- [BGE embedding models](https://huggingface.co/BAAI/bge-large-zh-v1.5)
- [FAISS docs](https://github.com/facebookresearch/faiss)
- [Isolation Forest paper](https://cs.nju.edu.cn/zhouzh/zhouzh.files/publication/icdm08.pdf)
