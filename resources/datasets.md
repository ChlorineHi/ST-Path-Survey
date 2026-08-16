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
