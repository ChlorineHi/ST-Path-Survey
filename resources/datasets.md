# Datasets and Benchmark Resources

This page provides a curated collection of public datasets relevant to spatial transcriptomics–histopathology integration. It complements the representative dataset table in our survey with metadata, accessions, official access routes, benchmark uses, code, and supplementary mirror information.

Official repositories remain the primary source whenever available. A supplementary **ST-Survey** resource archive is maintained via [Baidu Netdisk](https://pan.baidu.com/s/1YGvVOuaUttkKS5lZyS7jmA?pwd=wq42), extraction code: `wq42`.

- Official sources are preferred and remain authoritative.
- The Baidu Netdisk folder is supplementary and was reported empty by the maintainer on 2026-10-07; no dataset is currently recorded as mirrored.
- The tables below link official sources; their mirror entries are `—` until actual uploads are checked.
- Redistribution depends on the original license and terms of use.

## Quick Access

- **Official dataset sources:** see the three catalog tables below and the [source notes](#source-notes-and-preprocessing-resources).
- **Machine-readable CSV:** [dataset_catalog.csv](dataset_catalog.csv).
- **Data access and mirror policy:** [ACCESS.md](ACCESS.md).
- **Supplementary resource archive:** [ST-Survey on Baidu Netdisk](https://pan.baidu.com/s/1YGvVOuaUttkKS5lZyS7jmA?pwd=wq42). Extraction code: `wq42`.

The shared archive is intended for representative datasets, lightweight processed files, metadata, annotations, or supplementary resources that can be redistributed under their corresponding licenses. Official repositories remain the authoritative source.

## Catalog Conventions

Metadata checked on **2026-10-07** against original publications, official archives, vendor dataset pages, and author repositories. Unknown fields use `Not specified` or `To be verified`. Task labels describe research uses or suitability conditional on obtaining the required modalities; they do not rank datasets or imply ready-made benchmark splits.

**No single benchmark captures the full ST–pathology problem.** The groups below organize datasets only. They preserve the survey framing of canonical spot-level benchmarks, disease-oriented cohorts, and cellular/subcellular resources; they do not alter the method taxonomy. cSCC and PDAC also serve as disease-oriented cohorts.

Scope describes the verified pairing in the selected release:

- `core`: matched histology and spatial molecular measurements directly support ST–pathology analysis.
- `boundary`: morphology or pathology supports annotation, segmentation, or limited supervision; direct histology pairing is not fully established for the selected public release.
- `adjacent`: spatial-omics resources without independently confirmed matched histopathology, useful for spatial biology benchmarking.

`Spatial Scale` uses Spot-level, High-density, Cellular, Subcellular, or Multi-scale. Cellular rows may also provide subcellular transcript coordinates. Array pitch, optical pixel size, and analysis binning are distinct quantities; see source notes for numerical scales. H&E and IF are distinguished explicitly.

**Mirror legend:** `—` means not mirrored. The maintainer reported that the common ST-Survey folder is empty on 2026-10-07, so all nine CSV rows use `mirror_status=not_mirrored` with an empty `mirror_url`. The folder link above is retained for future permitted uploads. Preparing or downloading files locally does not establish a public mirror. See [ACCESS.md](ACCESS.md#mirror-status).

## Canonical Spot-Level ST–Histology Benchmarks

The PDAC row is provisionally `boundary` because the official record verifies pathology annotation but public matched H&E and spatial files remain to be verified.

| Dataset / Resource | Species | Tissue / Disease | Technology | Spatial Scale | Morphology | Scale | Typical Tasks | Accession / ID | Official Access | Mirror | Reference |
|---|---|---|---|---|---|---|---|---|---|---|---|
| cSCC (Ji et al.) | Homo sapiens | Skin / Cutaneous squamous cell carcinoma | Spatial Transcriptomics (ST); 10x Visium validation | Spot-level | H&E + pathology annotation | 12 ST sections / 4 patients; 4 Visium sections / 2 additional patients | Spatial-domain identification; Histology-to-expression prediction; Tumor microenvironment analysis | GSE144239 (ST SubSeries); GSE144240 (SuperSeries) | [Official source](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144239) | — | [Reference](#reference-cscc) |
| DLPFC / spatialLIBD (HumanPilot) | Homo sapiens | Dorsolateral prefrontal cortex / Neurotypical donors | 10x Visium | Spot-level | H&E + cortical-layer annotation | 12 sections / 3 donors | Spatial-domain identification; Morphology-aware clustering; Cross-dataset benchmarking | 151507; 151508; 151509; 151510; 151669; 151670; 151671; 151672; 151673; 151674; 151675; 151676 | [Official source](https://github.com/LieberInstitute/HumanPilot#access-the-data) | — | [Reference](#reference-dlpfc) |
| HER2ST | Homo sapiens | Breast / HER2-positive breast cancer | Spatial Transcriptomics (original ST arrays) | Spot-level | H&E + pathology annotation | 36 sections / 8 patients; 8 pathologist-annotated sections | Histology-to-expression prediction; Tumor heterogeneity analysis; Spatial-domain identification | 10.5281/zenodo.4751624 (version 3.0) | [Official source](https://zenodo.org/records/4751624) | — | [Reference](#reference-her2st) |
| PDAC (Yousuf et al.) | Homo sapiens | Pancreas / Pancreatic ductal adenocarcinoma | 10x Visium | Spot-level | Histology-based pathology annotation; H&E: To be verified | 8 sections; patient count: Not specified | Tumor microenvironment analysis; Cell-type annotation; Spatial-domain identification (requires spatial files) | GSE205354 | [Official source](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE205354) | — | [Reference](#reference-pdac) |

## Large-Scale Multimodal Collections

| Dataset / Resource | Species | Tissue / Disease | Technology | Spatial Scale | Morphology | Scale | Typical Tasks | Accession / ID | Official Access | Mirror | Reference |
|---|---|---|---|---|---|---|---|---|---|---|---|
| HEST-1K (NeurIPS 2024 paper cohort) | Homo sapiens; Mus musculus | 26 organs / Multiple conditions; 25 cancer types | ST; 10x Visium; Visium HD; Xenium | Multi-scale | Paired H&E whole-slide images | 1,229 ST profiles / 153 cohorts / 26 organs | Histology-to-expression prediction; Cross-modal representation learning; Foundation-model pretraining; Cross-dataset benchmarking | MahmoodLab/hest (Hugging Face dataset ID) | [Official source](https://huggingface.co/datasets/MahmoodLab/hest) | — | [Reference](#reference-hest) |

The HEST-1K row describes the NeurIPS 2024 paper cohort. Its live access endpoint includes later expansions. Do not replace the paper's 1,229 profiles / 153 cohorts with counts from a later release.

## High-Resolution Spatial Resources

CosMx is `boundary` (IF morphology for segmentation). Stereo-seq/MOSTA is `adjacent` (no matched H&E confirmed). Visium HD and the selected Xenium release are `core`. These scope labels are recorded in the CSV.

| Dataset / Resource | Species | Tissue / Disease | Technology | Spatial Scale | Morphology | Scale | Typical Tasks | Accession / ID | Official Access | Mirror | Reference |
|---|---|---|---|---|---|---|---|---|---|---|---|
| CosMx NSCLC FFPE (prototype release) | Homo sapiens | Lung / Non-small-cell lung cancer | CosMx SMI prototype (targeted 960-plex RNA imaging) | Cellular | IF morphology (antibody-based segmentation); matched H&E: To be verified | 8 samples from 5 tissues; total cells: Not specified | Cell-type annotation; Niche analysis; Tumor microenvironment analysis | Not specified | [Official source](https://brukerspatialbiology.com/products/cosmx-spatial-molecular-imager/ffpe-dataset/nsclc-ffpe-dataset/) | — | [Reference](#reference-cosmx) |
| Stereo-seq / MOSTA | Mus musculus | Whole embryo / multiple developing organs / Developmental atlas | Stereo-seq (DNA nanoball-patterned arrays) | High-density | No matched H&E confirmed; anatomical context | Section count: To be verified | Spatial-domain identification; Cell-type annotation; Developmental atlas analysis | CNP0001543 | [Official source](https://db.cngb.org/stomics/mosta/) | — | [Reference](#reference-stereo) |
| Visium HD human colorectal cancer (FFPE, 10x release) | Homo sapiens | Sigmoid colon / Colorectal cancer | Visium HD Spatial Gene Expression (probe-based; pre-release protocol) | High-density | H&E | 1 section / 1 donor | Tumor microenvironment analysis; Spatial-domain identification; Super-resolution | visium-hd-cytassist-gene-expression-libraries-of-human-crc (10x page ID) | [Official source](https://www.10xgenomics.com/datasets/visium-hd-cytassist-gene-expression-libraries-of-human-crc) | — | [Reference](#reference-visiumhd) |
| Xenium breast biomarkers (FFPE, 10x release) | Homo sapiens | Breast / Breast cancer (IDC/DCIS) and one normal sample | Xenium v1 (targeted imaging; custom 280-gene panel) | Cellular | Post-Xenium H&E + fluorescence morphology | 12 samples / 12 donors | Cell-type annotation; Tumor microenvironment analysis; Histology-to-expression prediction | xenium-ffpe-human-breast-biomarkers (10x page ID) | [Official source](https://www.10xgenomics.com/datasets/xenium-ffpe-human-breast-biomarkers) | — | [Reference](#reference-xenium) |

## Source Notes and Preprocessing Resources

### cSCC

- [GEO ST SubSeries GSE144239](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144239) contains 16 sample records: P2/P5/P9/P10, three original ST replicates each; P4/P6, two Visium replicates each. [GSE144240](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144240) is the multimodal SuperSeries. The original 12-section ST subset and the Visium validation subset must be distinguished in benchmarks.
- The original paper's Fig. 3 and Fig. S3 document H&E and tumor-leading-edge annotations. [NCBI MINiML metadata](https://ftp.ncbi.nlm.nih.gov/geo/series/GSE144nnn/GSE144239/miniml/GSE144239_family.xml.tgz) provides sample identities and protocols when the GEO viewer presents a browser challenge. [ST Pipeline](https://github.com/SpatialTranscriptomicsResearch/st_pipeline) is upstream preprocessing software cited by the paper.

### DLPFC / spatialLIBD

- [HumanPilot](https://github.com/LieberInstitute/HumanPilot) documents three subjects and two pairs of adjacent sections per subject, with layer/white-matter labels. The author's [file manifest](https://github.com/LieberInstitute/HumanPilot/blob/master/AWS_File_locations.tsv) lists the 12 sample IDs recorded in the CSV and per-sample matrices/images.
- [spatialLIBD](https://research.libd.org/spatialLIBD/) supplies ExperimentHub access and workflows. The paper's data-availability statement directs raw FASTQs and raw images to [Globus](https://research.libd.org/globus/), endpoint `jhpce#HumanPilot10x`. A sample ID is not a GEO accession.

### HER2ST

- [Andersson et al.](https://www.nature.com/articles/s41467-021-26271-2) reports eight patients and 36 ST sections; the separate Visium validation dataset is not the original HER2ST acquisition technology.
- [Zenodo version 3.0](https://zenodo.org/records/4751624) contains processed counts, H&E images, pathologist labels and spot-to-pixel mappings. Only one section per patient is pathologist-annotated. The [author repository](https://github.com/almaan/her2st) supplies analysis scripts and archive-password guidance; use the guidance for the version actually downloaded.

### PDAC

- [GSE205354](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE205354) and its [MINiML record](https://ftp.ncbi.nlm.nih.gov/geo/series/GSE205nnn/GSE205354/miniml/GSE205354_family.xml.tgz) confirm eight fresh-frozen Visium sections, GSM6210834–GSM6210841, and pathologist annotation transferred to spots.
- The metadata describes matrices, barcodes and features. Public matched H&E images, spatial coordinates and annotation files are **To be verified**; the study's acquisition/annotation claims do not establish a complete public multimodal download. Patient count is **Not specified** in the checked archive metadata. Obtain those files before image-based or spatial benchmarking. No official study-specific code repository was verified.

### HEST-1K

- [NeurIPS 2024 proceedings](https://proceedings.neurips.cc/paper_files/paper/2024/hash/60a899cc31f763be0bde781a75e04458-Abstract-Datasets_and_Benchmarks_Track.html) verifies 1,229 ST profiles, 153 cohorts and 26 organs. The [paper](https://proceedings.neurips.cc/paper_files/paper/2024/file/60a899cc31f763be0bde781a75e04458-Paper-Datasets_and_Benchmarks_Track.pdf), Sec. 3.1 / Fig. 1, lists ST, Visium, Visium HD and Xenium.
- The [official library](https://github.com/mahmoodlab/HEST) provides querying, preprocessing, alignment and benchmark tutorials. The [Hugging Face card](https://huggingface.co/datasets/MahmoodLab/hest) states **CC BY-NC-SA 4.0** and gated access requiring acceptance of conditions. Pin the metadata release and exact sample IDs; the live collection has expanded beyond the paper cohort. Cite source cohorts as well as HEST where applicable.

### CosMx NSCLC

- The [official prototype NSCLC release](https://brukerspatialbiology.com/products/cosmx-spatial-molecular-imager/ffpe-dataset/nsclc-ffpe-dataset/) describes eight samples from five tissues and a **960-plex RNA panel**. The associated technology paper describes 980 RNAs / 108 proteins across its experiments; that broader figure is not the panel specification of this selected release.
- [He et al.](https://www.nature.com/articles/s41587-022-01483-z) describes antibody-based morphological segmentation and subcellular RNA localization. Record this as **IF morphology**, not H&E. Total cells for this release are **Not specified** here: 135,707 cells on the vendor page describes a single illustrated section, not all eight samples. Numerical localization precision and public matched H&E pairing are **To be verified**.

### Stereo-seq / MOSTA

- [MOSTA](https://db.cngb.org/stomics/mosta/) provides the mouse developmental atlas; [CNP0001543](https://db.cngb.org/data_resources/project/CNP0001543) is the raw-data archive linked by [Chen et al.](https://doi.org/10.1016/j.cell.2022.04.003). [SAW](https://github.com/BGIResearch/SAW) is the author-linked processing workflow.
- [STOmics technical explanation](https://en.stomics.tech/news/stomics-blog/1017.html) distinguishes **220 nm DNB diameter** and **500 nm center-to-center pitch** from binned or cell-segmented analysis. Effective resolution depends on binning/segmentation. Matched standard H&E is not independently confirmed for this atlas, so it remains `adjacent`. Section count and dataset redistribution license are **To be verified**.

### Visium HD CRC

- The [10x one-sample release](https://www.10xgenomics.com/datasets/visium-hd-cytassist-gene-expression-libraries-of-human-crc) verifies sigmoid-colon CRC, one donor/section, H&E, a late-development Visium HD protocol, Human Transcriptome Probe Set v2.0 and Space Ranger 3.0.0; it was released on 2024-03-25 under **CC BY 4.0**.
- [Space Ranger documentation](https://www.10xgenomics.com/support/software/space-ranger/latest/analysis/outputs/space-ranger-feature-barcode-matrices) specifies native **2 × 2 µm** squares and standard **8/16 µm** analysis bins. The linked [Nature Genetics study](https://doi.org/10.1038/s41588-025-02193-3) and [official analysis code](https://github.com/10XGenomics/HumanColonCancer_VisiumHD) concern a broader cohort archived under [GSE280318](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE280318); that SuperSeries is not a one-sample identifier.

### Xenium breast biomarkers

- The [selected 10x release](https://www.10xgenomics.com/datasets/xenium-ffpe-human-breast-biomarkers) verifies 12 samples / 12 vendor-reported donors, breast IDC/DCIS and one normal sample, a custom **280-gene** panel, Xenium v1, and Onboard Analysis 4.0.0. It was released on 2025-12-11 under **CC BY 4.0**.
- The same page documents post-Xenium H&E using CG000613 and links instructions for image/alignment import. It supplies cellular outputs and transcript coordinates; it is **targeted imaging-based ST**, not whole-transcriptome sequencing. Per-sample cell counts are available on the vendor page; no collection total is inferred here. The vendor links the [companion preprint](https://www.biorxiv.org/content/10.64898/2025.12.08.692193v1).

## References

### Reference cSCC

Ji et al. **Multimodal Analysis of Composition and Spatial Architecture in Human Squamous Cell Carcinoma.** *Cell* 182, 497–514.e22 (2020). [DOI: 10.1016/j.cell.2020.05.039](https://doi.org/10.1016/j.cell.2020.05.039).

### Reference DLPFC

Maynard et al. **Transcriptome-scale spatial gene expression in the human dorsolateral prefrontal cortex.** *Nature Neuroscience* 24, 425–436 (2021). [DOI: 10.1038/s41593-020-00787-0](https://doi.org/10.1038/s41593-020-00787-0).

### Reference HER2ST

Andersson et al. **Spatial deconvolution of HER2-positive breast cancer delineates tumor-associated cell type interactions.** *Nature Communications* 12, 6012 (2021). [DOI: 10.1038/s41467-021-26271-2](https://doi.org/10.1038/s41467-021-26271-2). Dataset version: [10.5281/zenodo.4751624](https://zenodo.org/records/4751624).

### Reference PDAC

Yousuf et al. **Spatially Resolved Multi-Omics Single-Cell Analyses Inform Mechanisms of Immune Dysfunction in Pancreatic Cancer.** *Gastroenterology* 165, 891–908.e14 (2023). [DOI: 10.1053/j.gastro.2023.05.036](https://doi.org/10.1053/j.gastro.2023.05.036). [PubMed](https://pubmed.ncbi.nlm.nih.gov/37263303/).

### Reference HEST

Jaume et al. **HEST-1k: A Dataset For Spatial Transcriptomics and Histology Image Analysis.** *Advances in Neural Information Processing Systems* 37, Datasets and Benchmarks Track (2024). [Proceedings / DOI: 10.52202/079017-1704](https://proceedings.neurips.cc/paper_files/paper/2024/hash/60a899cc31f763be0bde781a75e04458-Abstract-Datasets_and_Benchmarks_Track.html).

### Reference CosMx

He et al. **High-plex imaging of RNA and proteins at subcellular resolution in fixed tissue by spatial molecular imaging.** *Nature Biotechnology* 40, 1794–1806 (2022). [DOI: 10.1038/s41587-022-01483-z](https://doi.org/10.1038/s41587-022-01483-z).

### Reference Stereo

Chen et al. **Spatiotemporal transcriptomic atlas of mouse organogenesis using DNA nanoball-patterned arrays.** *Cell* 185, 1777–1792.e21 (2022). [DOI: 10.1016/j.cell.2022.04.003](https://doi.org/10.1016/j.cell.2022.04.003).

### Reference VisiumHD

**High-definition spatial transcriptomic profiling of immune cell populations in colorectal cancer.** *Nature Genetics* (2025). [DOI: 10.1038/s41588-025-02193-3](https://doi.org/10.1038/s41588-025-02193-3). The vendor dataset page explicitly links this study.

### Reference Xenium

**Biomarker Quantification in Breast Cancer using Xenium In Situ.** *bioRxiv* preprint (2025), linked by the official dataset page. [DOI: 10.64898/2025.12.08.692193](https://www.biorxiv.org/content/10.64898/2025.12.08.692193v1). Preprint full text was not independently accessible during this check; dataset metadata above comes from the official 10x page.

## Shared Resources

The **ST-Survey** shared archive is maintained as a supplementary resource collection on [Baidu Netdisk](https://pan.baidu.com/s/1YGvVOuaUttkKS5lZyS7jmA?pwd=wq42). Extraction code: `wq42`.

It is intended to reduce repeated manual retrieval of commonly used public resources. Selected datasets, annotations, metadata, processed files, or supplementary resources may be included where redistribution is permitted. **The maintainer reported the folder empty on 2026-10-07. No datasets have been uploaded or confirmed mirrored in this session.** No dataset-specific mirror path or filename is asserted.

Users should cite the original dataset publications and repositories rather than the mirror itself. The mirror is an access convenience, not the original data source.

## Extending the Catalog

Add a CSV record and a matching row/source note in the relevant table. Keep the 18 CSV columns in their current order; place publication year, venue, license, verification date, numerical scale details and additional primary-source URLs in `notes`. Semicolons delimit multiple values within a cell; CSV quoting handles commas. `official_url` and `mirror_url` each contain one URL.

Allowed `scope` values: `core`, `boundary`, `adjacent`. Allowed `mirror_status` values: `available`, `shared_archive`, `not_mirrored`, `unknown`. Update a row to `available` only after checking the actual shared files and their license. See [ACCESS.md](ACCESS.md) for evidence requirements.

Future processed datasets, benchmark splits, preprocessing scripts and model-ready files should document original accessions, sample IDs, registration/QC, gene sets, split unit, processing version, license and checksums. Add files or directories only when corresponding resources actually exist. Related method code remains in the [method catalog](methods.md) and [root library index](../README.md#useful-libraries).

## Existing Dataset Guide

The original resource-discovery, platform-regime and evaluation guidance is retained below.

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
