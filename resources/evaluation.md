# Evaluation framework

ST–pathology models should be evaluated at the level of their intended biological and computational claim. Aggregate prediction metrics alone are insufficient for generative, retrieval, foundation-model, and knowledge-grounded systems.

## Metric families

| Claim / task | Core metrics | Complementary checks |
|---|---|---|
| Spatial-domain identification | ARI, NMI, AMI | Spatial continuity, boundary agreement, stability across seeds |
| Expression prediction | Gene-wise and spot-wise PCC/Spearman, MAE, RMSE | Marker-gene recovery, pathway preservation, uncertainty calibration |
| Super-resolution / imputation | PCC/Spearman, error metrics | Spatial autocorrelation, cell-type consistency, held-out high-resolution reference |
| Cross-modal retrieval | Recall@K, median rank, retrieval accuracy | Tissue- and patient-disjoint retrieval; hard-negative analysis |
| Cell/niche annotation | Macro-F1, balanced accuracy | Rare-class performance, ontology consistency, neighborhood preservation |
| Generative modeling | Distributional and reconstruction metrics | Valid spatial programs, pathway consistency, uncertainty and failure cases |
| Evidence-grounded interpretation | Evidence precision/recall, expert rating | Source traceability, executable reproduction, unsupported-claim rate |
| Transfer and robustness | External-cohort delta, domain-shift performance | Cross-platform, cross-tissue, cross-site, and ablation results |

## Minimum reporting protocol

1. **Declare the split unit.** Prefer patient- or slide-disjoint splits over random spots.
2. **Report central tendency and uncertainty.** Include repeated seeds, confidence intervals, or both.
3. **Use matched baselines.** Keep preprocessing, image encoder, gene set, and split identical when possible.
4. **Separate seen and unseen regimes.** Distinguish within-cohort performance from cross-patient, cross-tissue, and cross-platform transfer.
5. **Include mechanism ablations.** Remove each claimed fusion component, biological prior, or pretraining source.
6. **Check biological fidelity.** Evaluate marker localization, pathways, cell states, spatial niches, and gene–gene structure.
7. **Report resource cost.** State trainable parameters, hardware, runtime, memory, and inference resolution.
8. **Document failure cases.** Include low-quality tissue, registration error, rare cell states, and domain shift.

## Recommended interpretation

A numerically stronger model should not be described as biologically superior unless it also preserves relevant molecular programs and spatial organization. Similarly, a fluent language-model explanation should not be considered evidence-grounded unless claims can be traced to retrieved sources or reproducible analyses.
