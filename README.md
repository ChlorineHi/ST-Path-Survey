# Awesome Spatial Transcriptomics × Pathology

### Papers, methods, datasets, foundation models, benchmarks, and tools for multimodal ST–pathology research

<p align="center">
  <img src="assets/figures/taxonomy.jpg" alt="Taxonomy of multimodal fusion for spatial transcriptomics and pathology" width="100%">
</p>

<p align="center">
  <a href="https://github.com/ChlorineHi/ST-Path-Survey/stargazers"><img src="https://img.shields.io/github/stars/ChlorineHi/ST-Path-Survey?style=social" alt="GitHub stars"></a>
  <img src="https://img.shields.io/badge/literature-2020--2026-1f6feb" alt="Literature coverage 2020–2026">
  <img src="https://img.shields.io/badge/status-living%20survey-2ea44f" alt="Living survey">
</p>

This repository accompanies **From Representation Learning to Foundation Models: A Survey of Multimodal Fusion for Spatial Transcriptomics and Pathology** by Jingxuan Wang and Dayu Hu. It is a curated, living index of work connecting tissue morphology with spatial molecular measurements.

Methods are classified by their **dominant fusion mechanism**. Foundation models are a cross-cutting scaling trajectory, not a fourth fusion level.

> **Legend:** ● Core ST–pathology fusion · ◐ Boundary/transitional · ○ Adjacent support. `Paper` links point to a primary publication/preprint when verified; `Code` links point to an official implementation. `—` means no official public resource has been verified.

## Contents

- [Survey and benchmark papers](#survey-and-benchmark-papers)
- [Taxonomy at a glance](#taxonomy-at-a-glance)
- [A. Representation-level fusion](#a-representation-level-fusion)
- [B. Interaction-level fusion](#b-interaction-level-fusion)
- [C. Knowledge-constrained fusion](#c-knowledge-constrained-fusion)
- [D. Foundation-model scaling](#d-foundation-model-scaling)
- [Datasets and databases](#datasets-and-databases)
- [Benchmarks and evaluation](#benchmarks-and-evaluation)
- [Useful libraries](#useful-libraries)
- [Contributing](#contributing)

## Survey and benchmark papers

| Year | Resource | Venue | Links |
|---:|---|---|---|
| 2025 | Combining spatial transcriptomics with tissue morphology | Nature Communications | [Paper](https://www.nature.com/articles/s41467-025-58989-8) |
| 2025 | Benchmarking the translational potential of spatial gene expression prediction from histology | Nature Communications | [Paper](https://www.nature.com/articles/s41467-025-56618-y) |
| 2025 | Multi-Modal Foundation Models for Computational Pathology: A Survey | arXiv | [Paper](https://arxiv.org/abs/2503.09091) |
| 2024 | Deep learning-based multimodal spatial transcriptomics analysis for cancer | Advances in Cancer Research | [DOI](https://doi.org/10.1016/bs.acr.2024.08.001) |
| 2024 | Deep learning methods for spatial transcriptomics | Briefings in Bioinformatics | [Paper](https://academic.oup.com/bib/article/25/3/bbae181/7657952) |
| 2022 | Museum of Spatial Transcriptomics | Nature Methods | [Paper](https://www.nature.com/articles/s41592-022-01409-2) |

## Taxonomy at a glance

| Level | Diagnostic question | Families |
|---|---|---|
| **A. Representation** | What modality-specific representations are coupled? | Composition; co-decomposition; shared latent variables; metric/contrastive alignment |
| **B. Interaction** | How does one modality dynamically modify another? | Cross-attention; topology-mediated passing; reconstruction/generation; hybrid interaction |
| **C. Knowledge** | What biological knowledge constrains or regularizes fusion? | Pathways; ontologies; regulatory networks; evidence-grounded reasoning |
| **D. Scaling** | Which reusable encoders or paired pretraining schemes enable transfer? | Pathology FMs; spatial-omics FMs; paired morphomolecular FMs; language-enabled systems |

See [the full method catalog](resources/methods.md) for paper titles, mechanisms, tasks, and notes. Inclusion decisions follow [the scope criteria](resources/inclusion-criteria.md).

## A. Representation-level fusion

Fusion occurs primarily over modality-specific representations.

### A1. Feature composition

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | AESTETIK | Bioinformatics | ● | [Paper](https://academic.oup.com/bioinformatics) | — |
| 2024 | iIMPACT | Genome Biology | ● | [Paper](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-024-03289-5) | — |
| 2020 | SpaCell | Bioinformatics | ● | [Paper](https://academic.oup.com/bioinformatics/article/36/7/2293/5663455) | [Code](https://github.com/BiomedicalMachineLearning/SpaCell) |
| 2020 | stLearn | bioRxiv | ● | [Paper](https://doi.org/10.1101/2020.05.31.125658) | [Code](https://github.com/BiomedicalMachineLearning/stlearn_manuscript) |

### A2. Coupled factorization and co-decomposition

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | STORM | Briefings in Bioinformatics | ● | [Paper](https://academic.oup.com/bib/article/27/3/bbag324/8713039) | [Code](https://github.com/denizgurarslan/STORM) |
| 2025 | CellPie | Nucleic Acids Research | ◐ | [Paper](https://academic.oup.com/nar/article/53/6/gkaf251/8102295) | — |
| 2025 | FAST | BMC Bioinformatics | ◐ | [Search](https://bmcbioinformatics.biomedcentral.com/articles?query=FAST+spatial+transcriptomics) | — |
| 2023 | Nonnegative spatial factorization | Nature Methods | ○ | [Search](https://www.nature.com/search?q=Nonnegative%20spatial%20factorization) | — |

### A3. Shared latent-variable modeling

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | SpaHDmap | Preprint | ● | — | — |
| 2025 | Starfysh | Nature Biotechnology | ● | [Paper](https://www.nature.com/articles/s41587-024-02173-8) | — |
| 2025 | SpatialMETA | Nature Communications | ◐ | [Paper](https://www.nature.com/articles/s41467-025-63915-z) | — |
| 2022 | MUSE | Nature Biotechnology | ● | [Paper](https://www.nature.com/articles/s41587-022-01255-1) | [Code](https://github.com/AltschulerWu-Lab/MUSE) |

### A4. Metric and contrastive alignment

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | FineST | Nature Communications | ● | [Paper](https://www.nature.com/articles/s41467-026-70528-7) | — |
| 2026 | SpaConTDS | PLOS Computational Biology | ● | [Search](https://journals.plos.org/ploscompbiol/search?q=SpaConTDS) | — |
| 2025 | MAGIC | Briefings in Bioinformatics | ● | [DOI](https://doi.org/10.1093/bib/bbaf317) | — |
| 2025 | TriCLFF | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=TriCLFF) | — |
| 2024 | mclSTExp | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=mclSTExp) | — |
| 2023 | BLEEP | NeurIPS | ● | [Paper](https://proceedings.neurips.cc/paper_files/paper/2023/hash/51a2d4a84ac0e1597d49ba1abca1812f-Abstract-Conference.html) | [Code](https://github.com/bowang-lab/BLEEP) |
| 2023 | ConGI | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=ConGI) | — |
| 2022 | conST | bioRxiv | ● | [Paper](https://doi.org/10.1101/2022.01.14.476408) | [Code](https://github.com/ys-zong/conST) |

## B. Interaction-level fusion

One modality dynamically changes another modality's representation, topology, reconstruction, or generation inside the model.

### B1. Attention-mediated interaction

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | SpaBiT | Bioinformatics | ● | [Search](https://academic.oup.com/bioinformatics/search-results?q=SpaBiT) | — |
| 2025 | HAGE | MICCAI | ● | [Search](https://link.springer.com/search?query=HAGE+spatial+transcriptomics) | — |
| 2025 | HISTEX | MICCAI | ● | [Search](https://link.springer.com/search?query=HISTEX+spatial+transcriptomics) | — |
| 2021 | HisToGene | bioRxiv | ● | [Search](https://www.biorxiv.org/search/HisToGene) | [Code](https://github.com/maxpmx/HisToGene) |

### B2. Topology-mediated message passing

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | stGCL | Genome Biology | ● | [Search](https://genomebiology.biomedcentral.com/articles?query=stGCL) | — |
| 2026 | stRGAT | Journal of Translational Medicine | ● | [Search](https://translational-medicine.biomedcentral.com/articles?query=stRGAT) | — |
| 2026 | STESH | PLOS Computational Biology | ● | [Search](https://journals.plos.org/ploscompbiol/search?q=STESH) | — |
| 2025 | SpaICL | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=SpaICL) | — |
| 2025 | StereoMM | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=StereoMM) | — |
| 2025 | STAIG | Nature Communications | ● | [Search](https://www.nature.com/search?q=STAIG) | — |
| 2024 | MCGAE | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=MCGAE) | — |
| 2024 | MVST | PLOS Computational Biology | ● | [Search](https://journals.plos.org/ploscompbiol/search?q=MVST) | — |
| 2024 | xSiGra | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=xSiGra) | — |
| 2023 | SiGra | Nature Communications | ● | [Paper](https://www.nature.com/articles/s41467-023-41437-w) | [Code](https://github.com/QSong-github/SiGra) |
| 2022 | DeepST | Nucleic Acids Research | ● | [Paper](https://academic.oup.com/nar/article/50/22/e131/6761987) | [Code](https://github.com/JiangBioLab/DeepST) |
| 2021 | SpaGCN | Nature Methods | ● | [Paper](https://www.nature.com/articles/s41592-021-01255-8) | [Code](https://github.com/jianhuupenn/SpaGCN) |

### B3. Reconstruction and conditional generation

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | HINGE | arXiv | ● | [Paper](https://arxiv.org/abs/2603.19766) | — |
| 2026 | STMDiT | bioRxiv | ● | [Search](https://www.biorxiv.org/search/STMDiT) | — |
| 2025 | HoloTea | arXiv | ● | [Paper](https://arxiv.org/abs/2511.14613) | — |
| 2025 | Stem | arXiv | ● | [Paper](https://arxiv.org/abs/2501.15598) | — |
| 2025 | STFlow | arXiv | ● | [Paper](https://arxiv.org/abs/2506.05361) | [Code](https://github.com/Graph-and-Geometric-Learning/STFlow) |
| 2025 | STPath | npj Digital Medicine | ● | [Paper](https://www.nature.com/articles/s41746-025-02020-3) | — |
| 2024 | Diff-ST | MICCAI | ● | [Search](https://link.springer.com/search?query=Cross-modal+diffusion+spatial+transcriptomics) | — |
| 2022 | XFuse | Nature Biotechnology | ● | [Paper](https://www.nature.com/articles/s41587-021-01075-3) | [Code](https://github.com/ludvb/xfuse) |

### B4. Hybrid and hierarchical interaction

| Year | Method | Venue | Scope | Paper | Code |
|---:|---|---|:---:|---|---|
| 2026 | HESpotEx | Nature Computational Science | ● | [Search](https://www.nature.com/search?q=HESpotEx) | — |
| 2026 | PH2ST | Medical Image Analysis | ● | [Search](https://www.sciencedirect.com/search?qs=PH2ST) | — |
| 2026 | STARS | Nature Communications | ● | [Search](https://www.nature.com/search?q=STARS+spatial+transcriptomics) | — |
| 2025 | BAF-MGNN | Pattern Recognition | ● | [Search](https://www.sciencedirect.com/search?qs=Bridging+attention+fusion+spatial+gene+expression) | — |
| 2025 | GHIST | Nature Methods | ● | [Paper](https://www.nature.com/articles/s41592-025-02795-z) | — |
| 2024 | HGGEP | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=hypergraph+gene+expression+histology) | — |
| 2024 | THItoGene | Briefings in Bioinformatics | ● | [Paper](https://pmc.ncbi.nlm.nih.gov/articles/PMC10749789/) | [Code](https://github.com/yrjia1015/THItoGene) |
| 2022 | Hist2ST | Briefings in Bioinformatics | ● | [Paper](https://academic.oup.com/bib/article/23/5/bbac297/6651147) | [Code](https://github.com/biomed-AI/Hist2ST) |

## C. Knowledge-constrained fusion

These methods inject structured knowledge or add an evidence-grounded interpretation layer. C4 systems are interpretation resources and are not automatically fusion backbones.

| ID | Year | Method | Knowledge source | Venue | Scope | Paper |
|:---:|---:|---|---|---|:---:|---|
| C1 | 2026 | PathCLAST | Pathways and gene programs | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=PathCLAST) |
| C1 | 2026 | PEaRL | Pathway-enhanced representation | WACV | ◐ | [Search](https://openaccess.thecvf.com/menu) |
| C1 | 2025 | Path-MGCN | Pathway activity | Briefings in Bioinformatics | ● | [Search](https://academic.oup.com/bib/search-results?q=Path-MGCN) |
| C2 | 2026 | MSGR | Gene Ontology hierarchy | arXiv | ● | [Paper](https://arxiv.org/abs/2608.00405) |
| C2 | 2025 | M2TGLGO | Gene similarity and ontology | CVPR | ● | [Search](https://openaccess.thecvf.com/CVPR2025) |
| C3 | 2026 | Logic-constrained gene–pathway KG | Gene-pathway heterogeneous KG | npj Biomedical Innovations | ◐ | [Search](https://www.nature.com/search?q=logic-constrained+gene-pathway) |
| C3 | 2025 | HEIST | Spatial graph foundation prior | arXiv | ○ | [Search](https://arxiv.org/search/?query=HEIST+spatial+transcriptomics&searchtype=all) |
| C4 | 2026 | ChatSpatial | Schemas, tools, and evidence | bioRxiv | ○ | [Search](https://www.biorxiv.org/search/ChatSpatial) |
| C4 | 2025 | SpatialAgent | Tool-augmented spatial analysis | bioRxiv | ○ | [Search](https://www.biorxiv.org/search/SpatialAgent) |
| C4 | 2025 | STAgent | Spatial-analysis agent | bioRxiv | ○ | [Search](https://www.biorxiv.org/search/STAgent) |

## D. Foundation-model scaling

### D1. Visual foundation models for pathology

| Year | Model | Relation to ST–pathology | Paper | Code/model |
|---:|---|---|---|---|
| 2026 | MINT | Molecularly informed pathology pretraining | [Paper](https://arxiv.org/abs/2603.07895) | — |
| 2026 | SEAL | ST-driven pathology FM | [Paper](https://arxiv.org/abs/2602.14177) | — |
| 2026 | STAMP | ST-guided pathology alignment | [Paper](https://arxiv.org/abs/2606.03644) | — |
| 2025 | TITAN | Transferable multimodal WSI encoder | [Paper](https://www.nature.com/articles/s41591-025-03982-3) | [Code](https://github.com/mahmoodlab/TITAN) |
| 2024 | Prov-GigaPath | Whole-slide pathology backbone | [Paper](https://www.nature.com/articles/s41586-024-07441-w) | [Code](https://github.com/prov-gigapath/prov-gigapath) |
| 2024 | UNI | General pathology encoder | [Paper](https://www.nature.com/articles/s41591-024-02857-3) | [Code](https://github.com/mahmoodlab/UNI) |
| 2024 | Virchow | Clinical-grade pathology FM | [Paper](https://www.nature.com/articles/s41591-024-03141-0) | [Model](https://huggingface.co/paige-ai/Virchow) |

### D2. Molecular and spatial-omics foundation models

| Year | Model | Modality | Paper | Code/model |
|---:|---|---|---|---|
| 2026 | SpatialFormer | Spatial omics | [Search](https://www.nature.com/search?q=SpatialFormer) | — |
| 2025 | HEIST | ST/proteomics graphs | [Search](https://arxiv.org/search/?query=HEIST+spatial+transcriptomics&searchtype=all) | — |
| 2025 | Nicheformer | Single-cell and spatial omics | [Search](https://www.nature.com/search?q=Nicheformer) | [Code](https://github.com/theislab/nicheformer) |
| 2025 | Novae | Graph-based ST | [Search](https://www.nature.com/search?q=Novae+spatial+transcriptomics) | [Code](https://github.com/MICS-Lab/novae) |
| 2025 | scGPT-spatial | Spatial continual pretraining | [Search](https://www.biorxiv.org/search/scGPT-spatial) | — |
| 2025 | SToFM | Multi-scale ST | [Paper](https://arxiv.org/abs/2507.11588) | — |
| 2024 | scGPT | Single-cell multi-omics | [Paper](https://www.nature.com/articles/s41592-024-02201-0) | [Code](https://github.com/bowang-lab/scGPT) |

### D3. Paired morphomolecular foundation models

| Year | Model | Pairing | Paper |
|---:|---|---|---|
| 2026 | STORM-FM | Histology + ST | [Paper](https://arxiv.org/abs/2604.03630) |
| 2026 | VOICE | Vision + omics | [Paper](https://arxiv.org/abs/2608.08366) |
| 2025 | FmH2ST | Histology → ST generation | [Search](https://academic.oup.com/nar/search-results?q=FmH2ST) |
| 2025 | OmiCLIP | Histopathology ↔ spatial omics | [Paper](https://www.nature.com/articles/s41592-025-02707-1) |
| 2025 | PAST | Histopathology + single-cell/ST | [Paper](https://arxiv.org/abs/2507.06418) |
| 2025 | STPath | WSI + ST generative pretraining | [Paper](https://www.nature.com/articles/s41746-025-02020-3) |
| 2024 | PathOmCLIP | Pathology + single-cell/ST | [Search](https://www.biorxiv.org/search/PathOmCLIP) |
| 2024 | ST-Align | Image–gene alignment | [Paper](https://arxiv.org/abs/2411.16793) |

### D4. Generative and language-enabled systems

| Year | System | Capability | Scope | Paper |
|---:|---|---|:---:|---|
| 2026 | spEMO | Spatial multi-omics and histopathology analysis | ● | [Search](https://www.nature.com/search?q=spEMO) |
| 2026 | HINGE | Histology-conditioned expression generation | ● | [Paper](https://arxiv.org/abs/2603.19766) |
| 2026 | ChatSpatial | Reproducible agentic orchestration | ○ | [Search](https://www.biorxiv.org/search/ChatSpatial) |
| 2025 | SpatialAgent | Autonomous spatial-biology analysis | ○ | [Search](https://www.biorxiv.org/search/SpatialAgent) |

## Datasets and databases

| Resource | Platform / regime | Paired information | Typical use | Access |
|---|---|---|---|---|
| Human DLPFC / spatialLIBD | 10x Visium | H&E, expression, cortical layers | Domains; representation learning | [Portal](https://research.libd.org/spatialDLPFC/) · [Package](https://research.libd.org/spatialLIBD/) |
| HER2ST breast cancer | Spatial Transcriptomics | H&E, counts, pathologist regions | Expression prediction; tumors | [Data/code](https://github.com/almaan/her2st) · [Paper](https://www.nature.com/articles/s41467-021-26271-2) |
| 10x public datasets | Visium, Visium HD, Xenium | Platform-dependent morphology/expression | Cross-platform benchmarking | [Datasets](https://www.10xgenomics.com/datasets) |
| MOSTA | Stereo-seq | Developmental expression/anatomy | Large-scale spatial modeling | [Portal](https://db.cngb.org/stomics/mosta/) |
| STOmicsDB | Multi-platform | Datasets, publications, tools | Discovery | [Portal](https://db.cngb.org/stomics/) · [DOI](https://doi.org/10.1093/nar/gkad933) |
| SODB | Multi-platform | Curated spatial-omics datasets/modules | Comparative analysis | [Paper](https://www.nature.com/articles/s41592-023-01773-7) |
| CosMx SMI public FFPE data | Single-cell/subcellular | RNA/protein and morphology | Cell typing; neighborhoods | [Datasets](https://nanostring.com/products/cosmx-spatial-molecular-imager/ffpe-dataset/) |

See [the dataset guide](resources/datasets.md) for platform regimes, cohort selection, metadata requirements, and leakage warnings.

## Benchmarks and evaluation

| Task | Numerical metrics | Biological / spatial checks |
|---|---|---|
| Spatial domains | ARI, NMI, AMI | Boundary agreement, continuity, pathology concordance |
| Expression prediction | Pearson/Spearman, MAE, RMSE | Marker recovery, pathway preservation, calibration |
| Super-resolution | Error/correlation at held-out locations | Spatial autocorrelation and structure recovery |
| Cross-modal retrieval | Recall@K, median rank | Patient-disjoint retrieval and hard negatives |
| Cell/niche annotation | Macro-F1, balanced accuracy | Rare-class stability and expert agreement |
| Interpretation | Evidence precision/coverage | Expert review, traceability, reproducibility |

Use patient- or slide-disjoint splits whenever generalization is claimed. Random spot splits leak neighboring tissue and slide-specific signal. See [resources/evaluation.md](resources/evaluation.md).

## Useful libraries

| Category | Resources | Purpose |
|---|---|---|
| Core analysis | [Scanpy](https://scanpy.readthedocs.io/) · [Seurat](https://satijalab.org/seurat/) | Single-cell/ST preprocessing |
| Spatial analysis | [Squidpy](https://squidpy.readthedocs.io/) · [Giotto](https://giottosuite.com/) · [spatialLIBD](https://research.libd.org/spatialLIBD/) | Graphs, neighborhoods, visualization |
| ST–pathology | [stLearn](https://stlearn.readthedocs.io/) · [SpaGCN](https://github.com/jianhuupenn/SpaGCN) · [DeepST](https://github.com/JiangBioLab/DeepST) | Morphology-aware spatial analysis |
| Expression prediction | [Hist2ST](https://github.com/biomed-AI/Hist2ST) · [THItoGene](https://github.com/yrjia1015/THItoGene) · [BLEEP](https://github.com/bowang-lab/BLEEP) · [STFlow](https://github.com/Graph-and-Geometric-Learning/STFlow) | Histology-to-expression modeling |
| Vendor pipelines | [Space Ranger](https://www.10xgenomics.com/support/software/space-ranger) · [Xenium Explorer](https://www.10xgenomics.com/support/software/xenium-explorer) · [AtoMx](https://nanostring.com/products/atomx-spatial-informatics-platform/) | Processing and visualization |
| Foundation models | [UNI](https://github.com/mahmoodlab/UNI) · [Prov-GigaPath](https://github.com/prov-gigapath/prov-gigapath) · [scGPT](https://github.com/bowang-lab/scGPT) · [Nicheformer](https://github.com/theislab/nicheformer) | Transferable encoders |

## Contributing

Corrections, new papers, official code, dataset accessions, and benchmark updates are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md). New entries should include year, method, full title, venue/status, primary paper, official code if available, task, taxonomy ID, and scope label.

## Citation

```bibtex
@article{wang2026stpathsurvey,
  title   = {From Representation Learning to Foundation Models: A Survey of Multimodal Fusion for Spatial Transcriptomics and Pathology},
  author  = {Wang, Jingxuan and Hu, Dayu},
  journal = {Manuscript in preparation},
  year    = {2026},
  url     = {https://github.com/ChlorineHi/ST-Path-Survey}
}
```

Third-party licenses and terms remain authoritative. Repository restructuring and maintenance were assisted by [OpenAI Codex](https://openai.com/codex/).

_Last updated: 2026-08-16_
