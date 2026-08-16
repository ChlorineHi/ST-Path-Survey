# Full method and paper catalog

This catalog expands the compact tables in the [project homepage](../README.md). Placement follows the method's **dominant fusion mechanism**, not an architecture keyword or downstream task. A method may appear in more than one table only when the survey discusses two materially different roles.

**Scope:** ● Core paired ST–pathology fusion · ◐ Boundary/transitional · ○ Adjacent support.

## A. Representation-level fusion

### A1. Feature composition and adaptive weighting

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | AESTETIK | Representation learning for multi-modal spatially resolved transcriptomics data | Bioinformatics | Domain discovery / multimodal embedding | ● |
| 2024 | iIMPACT | iIMPACT: integrating image and molecular profiles for spatial transcriptomics analysis | Genome Biology | Joint representation / tissue analysis | ● |
| 2020 | SpaCell | SpaCell: integrating tissue morphology and spatial gene expression to predict disease cells | Bioinformatics | Disease-region prediction | ● |
| 2020 | stLearn | Integrating spatial location, tissue morphology and gene expression to find cell types, interactions and trajectories | bioRxiv | Morphology-aware ST analysis | ● |

**Mechanism.** Concatenation, weighted summation, or adaptive gating combines image and molecular embeddings without deep token- or graph-level exchange.

### A2. Coupled factorization and co-decomposition

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | STORM | Spatial transcriptomics optimization by resolution via matrix factorization | Briefings in Bioinformatics | Resolution enhancement / factors | ● |
| 2025 | CellPie | A scalable spatial transcriptomics factor discovery method via joint non-negative matrix factorization | Nucleic Acids Research | Factor discovery | ◐ |
| 2025 | FAST | Flexible analysis of spatial transcriptomics data: a deconvolution approach | BMC Bioinformatics | Deconvolution | ◐ |
| 2023 | NNSF | Nonnegative spatial factorization applied to spatial genomics | Nature Methods | Interpretable spatial programs | ○ |

**Mechanism.** Joint NMF, matrix factorization, CCA/GCCA, or multi-view decomposition exposes shared factors. The family is useful when interpretability and structured discovery matter more than expressive cross-modal interaction.

### A3. Shared latent-variable modeling

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | SpaHDmap | SpaHDmap | Preprint | Shared latent mapping | ● |
| 2025 | Starfysh | Starfysh integrates spatial transcriptomic and histologic data to reveal heterogeneous tumor–immune hubs | Nature Biotechnology | Tumor–immune niches | ● |
| 2025 | SpatialMETA | Integrating cross-sample and cross-modal data for spatial transcriptomics and metabolomics with SpatialMETA | Nature Communications | Cross-sample integration | ◐ |
| 2022 | MUSE | Integrative spatial analysis of cell morphologies and transcriptional states with MUSE | Nature Biotechnology | Morphology–state integration | ● |

**Mechanism.** Modality-specific encoders/decoders learn a shared deterministic or probabilistic latent space, commonly with autoencoder or VAE objectives.

### A4. Metric and contrastive alignment

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | FineST | Contrastive learning integrates histology and spatial transcriptomics for nuclei-resolved ligand–receptor analysis | Nature Communications | Nuclei-resolved analysis | ● |
| 2026 | SpaConTDS | A multimodal contrastive learning framework for identifying spatial domains by tuple disturbing | PLOS Computational Biology | Spatial domains | ● |
| 2026 | stGCL | A versatile cross-modality fusion method based on multimodal graph contrastive learning | Genome Biology | Domains / integration | ● |
| 2025 | MAGIC | Spatial histology and gene-expression representation and generative learning via online self-distillation | Briefings in Bioinformatics | Expression representation / generation | ● |
| 2025 | STAIG | Image-aided graph contrastive learning for domain exploration and alignment-free integration | Nature Communications | Domains / integration | ● |
| 2025 | TriCLFF | A multimodal feature-fusion framework using contrastive learning for spatial-domain identification | Briefings in Bioinformatics | Spatial domains | ● |
| 2024 | Contrastive ST–histology | A contrastive learning approach to integrate spatial transcriptomics and histological images | CSBJ | Integration | ● |
| 2024 | mclSTExp | Multimodal contrastive learning for spatial gene-expression prediction using histology images | Briefings in Bioinformatics | Expression prediction | ● |
| 2023 | BLEEP | Spatially resolved gene-expression prediction from histology images via bi-modal contrastive learning | NeurIPS | Expression prediction / retrieval | ● |
| 2023 | ConGI | Identifying spatial domain by adapting transcriptomics with histology through contrastive learning | Briefings in Bioinformatics | Spatial domains | ● |
| 2022 | conST | An interpretable multimodal contrastive learning framework for spatial transcriptomics | bioRxiv | Domains / representation | ● |

**Mechanism.** Pairwise metric learning, InfoNCE, CLIP-style objectives, or graph contrastive losses align morphology with molecular profiles. Retrieval and robust cross-modal alignment are characteristic outputs.

## B. Interaction-level fusion

### B1. Attention-mediated cross-modal interaction

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | SpaBiT | Enhancing spatial transcriptomics resolution via bidirectional attention transformers | Bioinformatics | Super-resolution | ● |
| 2025 | HAGE | Hierarchical Alignment Gene-Enhanced Pathology Representation Learning with Spatial Transcriptomics | MICCAI | Pathology representation | ● |
| 2025 | HISTEX | Inferring super-resolved gene expression by integrating histology and ST with HISTEX | MICCAI | Super-resolution | ● |
| 2021 | HisToGene | Leveraging ST to predict super-resolution gene expression from histology images in tumors | bioRxiv | Expression prediction | ● |

**Mechanism.** Cross-attention, co-attention, joint-token attention, or prompt conditioning allows one modality to modify another during inference.

### B2. Topology-mediated message passing

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | stGCL | A versatile cross-modality fusion method based on multimodal graph contrastive learning | Genome Biology | Domains / integration | ● |
| 2026 | stRGAT | Identifying spatial domains via a relational graph attention network | Journal of Translational Medicine | Spatial domains | ● |
| 2026 | STESH | Histology-informed spatial-domain identification through multi-view graph convolutional networks | PLOS Computational Biology | Spatial domains | ● |
| 2025 | SpaICL | Image-guided curriculum strategy-based graph contrastive learning for ST clustering | Briefings in Bioinformatics | Clustering | ● |
| 2025 | STAIG | Image-aided graph contrastive learning for domain exploration and alignment-free integration | Nature Communications | Domains / integration | ● |
| 2025 | StereoMM | A graph-fusion model integrating spatial transcriptomic data and pathological images | Briefings in Bioinformatics | Multimodal integration | ● |
| 2024 | MCGAE | Unraveling tumor invasion through integrated multimodal spatial transcriptomics | Briefings in Bioinformatics | Tumor invasion / domains | ● |
| 2024 | MVST | Identifying spatial domains from multiple views using multi-view graph convolutional networks | PLOS Computational Biology | Spatial domains | ● |
| 2024 | xSiGra | Explainable model for single-cell spatial data elucidation | Briefings in Bioinformatics | Single-cell explanation | ● |
| 2023 | SiGra | Single-cell spatial elucidation through an image-augmented graph transformer | Nature Communications | Single-cell spatial inference | ● |
| 2022 | DeepST | Identifying spatial domains in spatial transcriptomics by deep learning | Nucleic Acids Research | Spatial domains | ● |
| 2021 | SpaGCN | Integrating expression, location and histology to identify spatial domains and variable genes | Nature Methods | Domains / SVGs | ● |

**Mechanism.** Spatial, morphology-aware, multi-view, heterogeneous, or hypergraph edges determine how molecular and image information propagates through a tissue topology.

### B3. Cross-modal reconstruction and conditional generation

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | HINGE | Adapting a pre-trained single-cell foundation model to spatial gene-expression generation from histology | arXiv | Expression generation | ● |
| 2026 | STMDiT | Transcriptomics-conditioned virtual tissue synthesis via diffusion transformers | bioRxiv | Virtual tissue synthesis | ● |
| 2025 | HoloTea | 3D-guided scalable flow matching for volumetric tissue ST from serial histology | arXiv | 3D ST generation | ● |
| 2025 | Stem | Diffusion generative modeling for spatially resolved gene-expression inference from histology | arXiv | Expression generation | ● |
| 2025 | STFlow | Scalable generation of spatial transcriptomics from histology via whole-slide flow matching | arXiv | Whole-slide generation | ● |
| 2025 | STPath | A generative foundation model for integrating spatial transcriptomics and whole-slide images | npj Digital Medicine | Generation / foundation model | ● |
| 2024 | Diff-ST | Cross-modal diffusion modelling for super-resolved spatial transcriptomics | MICCAI | Super-resolution | ● |
| 2022 | XFuse | Super-resolved spatial transcriptomics by deep data fusion | Nature Biotechnology | Super-resolution | ● |

**Mechanism.** The cross-modal objective reconstructs, imputes, diffuses, or generates one modality conditionally on the other. This family includes flow matching and multimodal super-resolution.

### B4. Hybrid and hierarchical interaction

| Year | Method | Paper title | Venue | Main use | Scope |
|---:|---|---|---|---|:---:|
| 2026 | HESpotEx | A dual-stream deep learning framework for spot-level gene-expression prediction from histology | Nature Computational Science | Expression prediction | ● |
| 2026 | PH2ST | Prompt-guided hypergraph learning for ST prediction in whole-slide images | Medical Image Analysis | WSI expression prediction | ● |
| 2026 | STARS | Decoding spatial transcriptomics across multicellular and subcellular resolutions | Nature Communications | Multi-resolution decoding | ● |
| 2025 | BAF-MGNN | Bridging attention fusion-based multi-view graph neural networks for spatial expression prediction | Pattern Recognition | Expression prediction | ● |
| 2025 | GHIST | Spatial gene expression at single-cell resolution from histology using deep learning | Nature Methods | Single-cell expression | ● |
| 2025 | StereoMM | A graph-fusion model integrating ST and pathological images | Briefings in Bioinformatics | Multimodal integration | ● |
| 2024 | HGGEP | Gene-expression prediction from histology images via hypergraph neural networks | Briefings in Bioinformatics | Expression prediction | ● |
| 2024 | THItoGene | A deep learning method for predicting spatial transcriptomics from histological images | Briefings in Bioinformatics | Expression prediction | ● |
| 2022 | Hist2ST | Spatial transcriptomics prediction from histology jointly through transformer and graph neural networks | Briefings in Bioinformatics | Expression prediction | ● |

**Mechanism.** Multiple interaction channels—attention plus graphs, local plus global context, or iterative co-updating—operate at different spatial scales.

## C. Knowledge-constrained fusion

### C1. Pathway and gene-program priors

| Year | Method | Paper title | Prior | Scope |
|---:|---|---|---|:---:|
| 2026 | PathCLAST | Pathway-augmented contrastive learning with attention for interpretable spatial transcriptomics | Pathway graphs / programs | ● |
| 2026 | PEaRL | Pathway-Enhanced Representation Learning for Gene and Pathway Expression Prediction from Histology | Pathways | ◐ |
| 2025 | Path-MGCN | A pathway activity-based multi-view graph convolutional network for determining spatial domains | Pathway activity | ● |

### C2. Ontology and cell-identity priors

| Year | Method | Paper title | Prior | Scope |
|---:|---|---|---|:---:|
| 2026 | MSGR | Gene Ontology-Guided Hierarchical Spatial Gene Expression Prediction from Histopathology Images | Gene Ontology | ● |
| 2025 | M2TGLGO | Multi-modal Topology-embedded Graph Learning for Spatially Resolved Genes Prediction | Gene similarity / ontology | ● |

### C3. Regulatory and molecular-network priors

| Year | Method | Paper title | Prior | Scope |
|---:|---|---|---|:---:|
| 2026 | Gene–pathway KG | Inferring signaling pathway abnormalities via a logic-constrained gene–pathway heterogeneous KG | Gene–pathway KG | ◐ |
| 2026 | FineST | Nuclei-resolved ligand–receptor analysis via histology–ST contrastive learning | Ligand–receptor network | ● |
| 2025 | HEIST | A Graph Foundation Model for Spatial Transcriptomics and Proteomics Data | Spatial molecular graph | ○ |
| 2025 | Path-MGCN | Pathway activity-based multi-view graph convolution | Pathway/network activity | ● |

### C4. Evidence-grounded retrieval and semantic constraints

| Year | System | Paper title | Role | Scope |
|---:|---|---|---|:---:|
| 2026 | ChatSpatial | Schema-Enforced Agentic Orchestration for Reproducible and Cross-Platform ST | Interpretation / workflow layer | ○ |
| 2025 | SpatialAgent | An autonomous AI agent for spatial biology | Tool-augmented analysis | ○ |
| 2025 | STAgent | Spatial transcriptomics AI agent charts hPSC-pancreas maturation in vivo | Analysis agent | ○ |

**Important.** C4 is an interpretation layer, not automatically a fusion backbone. A system is Core only if paired morphology and spatial molecular measurements are jointly modeled, rather than merely described after analysis.

## D. Foundation-model scaling

### D1. Visual foundation models: pathology backbones

| Year | Model | Paper title | Venue | Default scope |
|---:|---|---|---|:---:|
| 2026 | MINT | Molecularly Informed Training with Spatial Transcriptomics Supervision for Pathology Foundation Models | arXiv | ◐ |
| 2026 | SEAL | Towards Spatial Transcriptomics-driven Pathology Foundation Models | arXiv | ◐ |
| 2026 | STAMP | Spatial Transcriptomics-Guided Alignment Enhances Molecular Profiling in Pathology Foundation Model | arXiv | ◐ |
| 2025 | TITAN | A multimodal whole-slide foundation model for pathology | Nature Medicine | ○ |
| 2024 | Prov-GigaPath | A whole-slide foundation model for digital pathology from real-world data | Nature | ○ |
| 2024 | UNI | Towards a general-purpose foundation model for computational pathology | Nature Medicine | ○ |
| 2024 | Virchow | A foundation model for clinical-grade computational pathology and rare-cancer detection | Nature Medicine | ○ |

### D2. Molecular and spatial-omics foundation models

| Year | Model | Paper title | Venue | Default scope |
|---:|---|---|---|:---:|
| 2026 | SpatialFormer | Universal spatial representation learning from subcellular molecular to multicellular landscapes | Nature Computational Science | ○ |
| 2025 | HEIST | A Graph Foundation Model for Spatial Transcriptomics and Proteomics Data | arXiv | ○ |
| 2025 | Nicheformer | A foundation model for single-cell and spatial omics | Nature Methods | ○ |
| 2025 | Novae | A graph-based foundation model for spatial transcriptomics data | Nature Methods | ○ |
| 2025 | scGPT-spatial | Continual pretraining of single-cell foundation model for spatial transcriptomics | bioRxiv | ○ |
| 2025 | SToFM | A multi-scale foundation model for spatial transcriptomics | arXiv | ○ |
| 2024 | scGPT | Toward building a foundation model for single-cell multi-omics using generative AI | Nature Methods | ○ |

### D3. Paired morphomolecular foundation models

| Year | Model | Paper title | Venue | Scope |
|---:|---|---|---|:---:|
| 2026 | STORM-FM | A multimodal foundation model of spatial transcriptomics and histology for biological discovery and clinical prediction | arXiv | ● |
| 2026 | VOICE | A Vision–Omics Foundation Model for direct and retrieval-based in-situ single-cell expression prediction | arXiv | ● |
| 2025 | FmH2ST | Foundation model-based spatial transcriptomics generation from histological images | Nucleic Acids Research | ● |
| 2025 | OmiCLIP | A visual–omics foundation model to bridge histopathology with spatial transcriptomics | Nature Methods | ● |
| 2025 | PAST | A multimodal single-cell foundation model for histopathology and spatial transcriptomics in cancer | arXiv | ● |
| 2025 | STPath | A generative foundation model for integrating spatial transcriptomics and whole-slide images | npj Digital Medicine | ● |
| 2024 | PathOmCLIP | Connecting tumor histology with spatial expression via locally enhanced contrastive learning | bioRxiv | ● |
| 2024 | ST-Align | A multimodal foundation model for image–gene alignment in spatial transcriptomics | arXiv | ● |

### D4. Generative and language-enabled systems

| Year | System | Paper title | Primary role | Scope |
|---:|---|---|---|:---:|
| 2026 | spEMO | Leveraging multimodal foundation models for analysing spatial multi-omic and histopathology data | Multimodal biological analysis | ● |
| 2026 | HINGE | Adapting a pre-trained single-cell FM to spatial expression generation from histology | Conditional generation | ● |
| 2026 | ChatSpatial | Schema-enforced agentic orchestration for reproducible, cross-platform ST | Reproducible analysis agent | ○ |
| 2025 | SpatialAgent | An autonomous AI agent for spatial biology | Tool-augmented analysis | ○ |

## Application map

| Application | Most relevant families | Recommended evaluation |
|---|---|---|
| Spatial-domain identification | A1, A4, B2, C1 | ARI/NMI/AMI; spatial continuity; pathology boundary agreement |
| Histology-to-expression prediction | A4, B1, B3, B4, D3 | PCC/Spearman; MAE/RMSE; marker/pathway recovery |
| Super-resolution and imputation | B1, B3, B4 | Held-out-location error; autocorrelation; external validation |
| Cross-modal retrieval | A4, D3 | Recall@K; median rank; patient-disjoint testing |
| Cell/niche annotation | A3, B2, C2 | Macro-F1; balanced accuracy; expert agreement |
| Biological interpretation | C1–C4 | Evidence precision; traceability; expert review |

## Classification caveats

- A GNN belongs to B2 only when graph topology mediates multimodal exchange; a graph used only after unimodal encoding does not qualify automatically.
- A pathology foundation model remains Adjacent if it only supplies frozen image embeddings. It becomes Core when paired histology and spatial molecular data are explicitly aligned, reconstructed, or jointly pretrained.
- A method can use contrastive learning and graphs simultaneously. The dominant information-exchange mechanism determines its primary row; secondary roles can be cross-referenced.
- Preprint status, code availability, and venue should be updated when a peer-reviewed version or official repository appears.
