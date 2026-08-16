# Inclusion and classification criteria

## Literature scope

- **Coverage window:** January 2020 through August 2026, with earlier seminal work retained only when required to explain a fusion primitive.
- **Primary focus:** computational methods connecting spatially resolved transcriptomics or spatial omics with histopathology/morphology images.
- **Evidence types:** peer-reviewed articles and clearly labelled preprints. Dataset and software records should point to official repositories, publishers, or provider pages.
- **Exclusions:** purely unimodal ST analysis, generic computational pathology without a transferable role, non-spatial bulk-omics fusion, and papers with no identifiable relevance to the proposed taxonomy.

## Scope labels

| Label | Operational definition | Typical example |
|---|---|---|
| **Core** | Spatial molecular measurements and histopathology are jointly used in the same training or inference pipeline. | Paired image–expression contrastive pretraining |
| **Boundary / transitional** | Pathology is partial/indirect, or the method bridges toward fusion through prediction, graph construction, or transferable alignment. | Histology-to-expression prediction without bidirectional interaction |
| **Adjacent support** | The work does not perform ST–pathology fusion but supplies a reusable backbone, benchmark, knowledge resource, or interpretation paradigm. | A pathology-only or spatial-omics-only foundation model |

## Five decidable axes

Each method should be recorded using five technical axes:

| Axis | Allowed descriptions | Diagnostic question |
|---|---|---|
| Fusion object | Feature, token, graph, latent variable, generated sample, knowledge entity | What is actually fused? |
| Fusion timing | Early, intermediate, late/semantic | When does cross-modal integration occur? |
| Fusion mechanism | Composition, factorization, attention, message passing, reconstruction, generation, retrieval | How is information exchanged? |
| Learning objective | Reconstruction, contrastive, supervised prediction, clustering, adversarial, diffusion/flow, instruction tuning | What objective drives fusion? |
| Biological prior | Spatial adjacency, morphology, pathway, ontology, regulatory network, biomedical KG | Which domain constraint is used? |

## Primary-category decision rule

1. If independently encoded modality vectors are combined or aligned, classify the method as **representation-level**.
2. If modalities modify one another through attention, topology, reconstruction, or generation inside the architecture, classify it as **interaction-level**.
3. If a structured biological prior or external evidence actively constrains or regularizes fusion, classify it as **knowledge-constrained**.
4. If the principal contribution is scalable pretraining and transfer, record the appropriate **foundation-model family** in addition to the mechanism-level category.
5. For methods spanning multiple categories, choose one primary category based on the dominant operation and document secondary mechanisms in notes.

## Update procedure

For each new entry, verify the title, year, publication status, primary paper URL, official code/data URL, paired modalities, dominant mechanism, scope label, and downstream task. Classification changes should include one or two sentences of evidence from the method description rather than relying on the paper title.
