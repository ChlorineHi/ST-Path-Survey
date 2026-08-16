# Methodological taxonomy

This page follows the survey's revised taxonomy. Classification is based on a method's **dominant fusion mechanism**, not merely its architecture name or downstream task. A method may contain secondary components from other categories; those components do not automatically change its primary placement.

## A. Representation-level fusion

Fusion occurs primarily over modality-specific representations.

| ID | Family | Defining operation | Representative methods | Typical use |
|---|---|---|---|---|
| A1 | Feature composition | Concatenation, weighted sum, or adaptive weighting/gating of image and RNA features | SpaCell, stLearn, iIMPACT | Spatial domains; small paired datasets |
| A2 | Coupled factorization and co-decomposition | NMF/coupled NMF, matrix factorization, CCA/GCCA, or multi-view decomposition | stCNMF, RCTD, multimodal Seurat v5, UnionCom | Interpretable factors; structured discovery |
| A3 | Shared latent-variable modeling | AE/VAE or probabilistic shared latent spaces with modality-specific encoders/decoders | Stafysh, TG-ME, SpatialMETA, scVI-spatial | Denoising; missing-value modeling; alignment |
| A4 | Metric and contrastive alignment | Pairwise metric learning, InfoNCE, CLIP-style alignment, or graph contrastive learning | conST, ConGI, ConGCN/ConGaR, TriCLIF, SpaConTDS, BLEEP, mdSTExp, FineST | Robust alignment; cross-modal retrieval |

## B. Interaction-level fusion

One modality dynamically modifies the representation, topology, reconstruction, or generation of another inside the model.

| ID | Family | Defining operation | Representative methods | Typical use |
|---|---|---|---|---|
| B1 | Attention-mediated interaction | Cross-attention, co-attention, joint-token attention, or prompt-conditioned interaction | HisToGene, HISTEX, HAGE, PH2ST | Cross-modal dependency modeling |
| B2 | Topology-mediated message passing | Spatial or morphology-aware graphs, multi-view graphs, heterogeneous graphs, or hypergraphs | SpaGCN, DeepST, MVST, SiGra, HGGER | Spatial-domain discovery; neighborhood-aware inference |
| B3 | Reconstruction and conditional generation | Cross-modal reconstruction, diffusion, flow matching, conditional generation, or super-resolution | XFuse, Diff-ST, Stem, STFlow, STPath | Gene-expression prediction; imputation; synthesis |
| B4 | Hybrid and hierarchical interaction | Attention plus graphs, local–global interaction, hypergraph–Transformer coupling, or iterative co-updating | Hist2ST, THItoGene, HGGER, PH2ST, GHIST | Multiscale morphology–molecule reasoning |

## C. Knowledge-constrained fusion

Structured biological or external evidence constrains, regularizes, or validates multimodal fusion.

| ID | Family | Defining knowledge | Representative methods/systems | Role |
|---|---|---|---|---|
| C1 | Pathway and gene-program priors | Pathway graphs, gene modules, or functional programs | PathCLAST | Functional regularization and interpretation |
| C2 | Ontology and cell-identity priors | Gene Ontology, Cell Ontology, cell-type or tissue hierarchies | M2TGLGO | Semantically coherent prediction and annotation |
| C3 | Regulatory and molecular networks | GRNs, PPIs, TF–target networks, ligand–receptor networks, or biomedical KGs | Path-MGCN and emerging KG-guided models | Mechanistically structured molecular inference |
| C4 | Evidence-grounded reasoning | Retrieval-augmented reasoning, agent-based interpretation, or LLMs connected to knowledge bases/tools | SpatialAgent, ChatSpatial, RAG-based systems | Interpretation layer; not necessarily a fusion backbone |

## D. Foundation-model scaling

Foundation models are a cross-cutting evolutionary trajectory. Their placement depends on their training modalities and how they enter the ST–pathology pipeline.

| ID | Model family | Representative examples | Default scope interpretation |
|---|---|---|---|
| D1 | Visual foundation models (pathology backbones) | UNI, Virchow, TITAN | Adjacent/transferable image encoders unless paired ST is used |
| D2 | Molecular or spatial-omics foundation models | scGPT-spatial, Nicheformer, SToFM, Novae | Adjacent/transferable molecular encoders unless pathology is used |
| D3 | Paired morphomolecular foundation models | omicCLIP, ST-Align, STPath, Fmh2ST, PathOmCLIP | Core when trained or adapted with paired histology and spatial molecular data |

## Enabled applications

| Application | Main output | Suitable evaluation families |
|---|---|---|
| Spatial-domain identification | Tissue-domain labels or embeddings | ARI, NMI, AMI, spatial continuity |
| Gene-expression prediction | Spot/cell-level expression profiles | PCC/Spearman, MAE/RMSE, marker recovery |
| Super-resolution and imputation | Higher-resolution or completed molecular maps | Numerical error, spatial structure, biological fidelity |
| Cross-modal retrieval | Matched image/RNA regions | Recall@K, median rank, retrieval accuracy |
| Cell/niche annotation | Cell types, states, or neighborhoods | Macro-F1, balanced accuracy, annotation agreement |
| Biological interpretation | Pathways, mechanisms, or evidence-linked narratives | Evidence precision, expert review, reproducibility |

## Classification caveat

Architecture names alone are insufficient. For example, using a GNN does not automatically imply interaction-level fusion: the graph must mediate information exchange involving pathology and spatial molecular data. Likewise, a pathology foundation model remains adjacent support if it only supplies frozen image embeddings. Use the decision rules in [inclusion-criteria.md](inclusion-criteria.md) when adding a method.
