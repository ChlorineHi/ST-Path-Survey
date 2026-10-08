# Data Access

## Official Sources

Official repositories and archives are the authoritative data sources. Start with [the dataset catalog](datasets.md), its source notes, or [the machine-readable CSV](dataset_catalog.csv). Cite the original publications and dataset records. Author code, preprocessing instructions, sample IDs and release limitations are linked in the catalog.

## GitHub Release Downloads

Three selected ST–histology sample packages are available from [the 2026-10-07 GitHub Release](https://github.com/ChlorineHi/ST-Path-Survey/releases/tag/datasets-2026-10-07): human breast cancer (STDS0000027), mouse brain coronal section (STDS0000022), and human lymph node (STDS0000024). Their ZIPs total **167,059,611 bytes (167.1 MB)**.

The ZIPs include AnnData expression matrices, paired H&E PNGs, spatial positions/scale factors, original URLs, attribution and license notices. All expression barcodes were matched to the spatial-position tables before packaging. Uploaded GitHub asset sizes and server SHA256 values were checked against the local files. [Manifest](https://github.com/ChlorineHi/ST-Path-Survey/releases/download/datasets-2026-10-07/DATASET_MANIFEST.json) and [checksums](https://github.com/ChlorineHi/ST-Path-Survey/releases/download/datasets-2026-10-07/SHA256SUMS.txt) are also published.

The original 10x datasets state CC BY 4.0. These are single-section processed samples retrieved through STOmicsDB; they are not full cohorts, raw FASTQs or full-resolution WSI. The downloaded lymph-node representation has 4,039 observations, compared with 4,035 spots on the current vendor page; the package preserves and documents this difference. See [the catalog's downloadable samples](datasets.md#downloadable-representative-samples).

## Redistribution

Distribute sample packages only when the original license or terms permit redistribution. If permission is unclear, provide the official source link. Preserve source attribution and license notices in every published package.

The selected 10x Visium HD and Xenium pages state CC BY 4.0. HEST's dataset card states CC BY-NC-SA 4.0 and requires acceptance of access conditions. Check the exact release and original cohort terms before any redistribution. Publication or software licenses do not automatically establish dataset or third-party image licensing. The HER2ST version 3.0 [Zenodo API record](https://zenodo.org/api/records/4751624) also explicitly states CC BY 4.0; this is a dataset-record license, independently checked rather than inferred from its publication. Other entries' dataset redistribution licenses remain **To be verified**.

## Large Files

Large raw datasets are not stored directly in this GitHub repository. Do not commit raw matrices, whole-slide image collections or sequencing reads, or use Git LFS to host large public datasets. This catalog contains documentation and lightweight metadata only. The three representative processed packages are distributed as GitHub Release assets outside the code commit history.

## Processed Resources

Where permitted, lightweight processed matrices, annotations, metadata, benchmark splits, preprocessing scripts or model-ready files may be shared separately. Record source accession/URL, release and sample IDs, license, transformation and software versions, registration/QC, split unit, file size and checksum before claiming availability. Keep raw and processed resources distinguishable.

Three representative processed packages and their dataset-level GitHub Release mappings are now available as described above. No data binaries are committed to the repository. Add corresponding code-tree directories only when populated lightweight resources exist.

## Dataset-Specific Access Notes

- **DLPFC:** use the author manifest and spatialLIBD/ExperimentHub for processed data; the original article links Globus for raw FASTQs and images.
- **HER2ST:** use the versioned Zenodo record and the author's password guidance for that release. Pathology annotations cover only one section per patient.
- **cSCC:** select GSE144239 for ST, and identify the original-ST or Visium-validation subset explicitly. GSE144240 is the broader SuperSeries.
- **PDAC:** GEO verifies eight Visium sections and pathology annotation. Public image/coordinate/annotation files are **To be verified**, so matrices alone should not be treated as a complete image-paired benchmark.
- **HEST:** accept the official Hugging Face conditions and pin the metadata release and sample IDs. The live collection differs from the 2024 paper cohort.
- **Visium HD / Xenium:** use the selected vendor pages' output/supplemental and input-file tabs. Obtain the matching histology and alignment files; preserve the stated software version.
- **CosMx / MOSTA:** use the specific vendor/atlas release. IF or anatomical context does not establish matched H&E pairing.

## Broken Links

Open a [GitHub issue](https://github.com/ChlorineHi/ST-Path-Survey/issues) if an official or GitHub Release download link becomes unavailable. Include the dataset, accession/release, affected URL and the date/error observed. Browser challenges, gated downloads and rate limits should be distinguished from a missing resource.

During the 2026-10-07 check, the curated tables rendered successfully through GitHub's GFM renderer and all nine publication DOIs matched their registered titles through Crossref. Direct automated requests to some GEO, Bruker/CosMx and bioRxiv pages encountered browser challenges; 10x requests encountered rate limits even though the dataset pages were readable through the browsing tool. GEO sample metadata was independently read from NCBI's small MINiML archives. HEST downloads remain gated. These conditions do not establish a broken link or confirm file-level download access.
