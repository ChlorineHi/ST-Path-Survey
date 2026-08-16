# Datasets and benchmark resources

Platforms are not interchangeable with datasets. A platform defines a technical acquisition regime; a benchmark is a particular cohort with tissue context, paired modalities, preprocessing, annotations, and a split protocol.

## Representative resources

| Resource | Platform / resolution regime | Paired information | Common uses | Primary link |
|---|---|---|---|---|
| Human DLPFC / spatialLIBD | 10x Visium, spot level | H&E, expression, cortical-layer annotations | Spatial-domain identification; representation learning | [spatialLIBD](https://research.libd.org/spatialLIBD/) |
| 10x public spatial datasets | Visium / Visium HD / Xenium | Platform-dependent expression and morphology | General benchmarking; high-resolution studies | [10x datasets](https://www.10xgenomics.com/datasets) |
| HER2-positive breast cancer | Spatial Transcriptomics, spot level | H&E, counts, pathologist annotations | Expression prediction; tumor-region analysis | [Data and code](https://github.com/almaan/her2st) |
| CosMx SMI public FFPE datasets | Imaging-based, single-cell/subcellular | RNA ± protein and morphology | Cell annotation; neighborhood analysis | [CosMx datasets](https://nanostring.com/products/cosmx-spatial-molecular-imager/ffpe-dataset/) |
| MOSTA | Stereo-seq, high-resolution developmental atlas | Spatial expression and anatomical context | Developmental mapping; scalable spatial modeling | [MOSTA portal](https://db.cngb.org/stomics/mosta/) |
| STOmicsDB | Multi-platform database | Datasets, publications, tools, and metadata | Resource discovery and external validation | [STOmicsDB](https://db.cngb.org/stomics/) |
| SODB | Multi-platform spatial-omics database | Curated datasets and analysis modules | Dataset discovery and comparative analysis | [SODB paper](https://www.nature.com/articles/s41592-023-01773-7) |

## Common benchmark cohorts

| Cohort | Tissue / species | Paired modalities | Annotations commonly used | Representative tasks |
|---|---|---|---|---|
| spatialLIBD DLPFC | Human dorsolateral prefrontal cortex | Visium expression + H&E | Cortical layers and white matter | Domain identification; layer recovery |
| HER2ST | Human HER2-positive breast cancer | Spatial Transcriptomics + H&E | Tumor/pathologist regions | Expression prediction; tumor-region analysis |
| 10x Visium breast cancer | Human breast tumor | Visium expression + H&E | Dataset-dependent tissue regions | Expression prediction; domain discovery |
| 10x Visium prostate cancer | Human prostate tumor | Visium expression + H&E | Dataset-dependent regions | Cross-tissue transfer; prediction |
| Mouse brain Visium | Mouse brain | Visium expression + H&E | Anatomical regions | Domain identification; spatial continuity |
| MOSTA | Mouse organogenesis | Stereo-seq expression + anatomical context | Developmental stages and organs | Scalable spatial representation learning |
| CosMx FFPE collections | Human FFPE tissues | Targeted RNA/protein + morphology | Cell types and tissue compartments | Cell typing; niche analysis |

These names describe families of releases, not a single immutable benchmark. Record the exact accession, sample list, preprocessing version, gene set, and split file in every experiment.

## Platform regimes

| Regime | Examples | Modeling consequence |
|---|---|---|
| Spot-based transcriptome-wide | Spatial Transcriptomics, Visium | Multiple cells per spot; morphology and counts must be registered at spot scale |
| High-definition bead/grid | Visium HD, Stereo-seq | Much larger graphs and stronger local dependence; split leakage becomes more severe |
| Imaging-based targeted RNA | Xenium, CosMx, MERFISH | Single-cell/subcellular coordinates but a restricted gene panel; cell segmentation affects labels |
| Serial-section / volumetric | Consecutive H&E and ST sections | Registration uncertainty and missing tissue complicate 3D reconstruction |

## Resource discovery portals

- [10x Genomics datasets](https://www.10xgenomics.com/datasets) — official Visium, Visium HD, and Xenium example data.
- [STOmicsDB](https://db.cngb.org/stomics/) — multi-platform spatial-transcriptomics data, metadata, publications, and analysis resources.
- [MOSTA](https://db.cngb.org/stomics/mosta/) — mouse organogenesis atlas generated with Stereo-seq.
- [SODB](https://www.nature.com/articles/s41592-023-01773-7) — curated spatial-omics database and interactive analysis resource.
- [spatialLIBD](https://research.libd.org/spatialLIBD/) — DLPFC data access and Bioconductor workflows.

## Dataset selection checklist

Before reporting a benchmark result, record:

- tissue, disease state, species, sample and patient counts;
- acquisition platform, nominal spatial resolution, gene panel/coverage, and image stain;
- registration and quality-control procedure;
- annotation source and whether labels were used during training;
- train/validation/test split unit (spots, slides, patients, tissues, or sites);
- whether external-cohort or cross-platform testing was performed; and
- public accession, preprocessing version, and code used to construct the benchmark.

## Leakage warning

Random spot-level splits can place neighboring spots or spots from the same slide in both training and test sets. This inflates performance by leaking patient-, slide-, and local-tissue-specific information. Patient- or slide-disjoint evaluation should therefore be preferred for claims of generalization.
