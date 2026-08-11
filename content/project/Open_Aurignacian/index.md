---
title: The Open Aurignacian Project
summary: An open-access database of 2,016 3D models of stone tools from four Early Upper Paleolithic sequences in Italy.

tags:
  - Aurignacian
  - 3D lithics
  - Open Science
date: '2020-09-27T00:00:00Z'

# Optional external URL for project (replaces project detail page).
#external_link: 'https://gepris.dfg.de/gepris/projekt/431809858?language=en'

# image:
#     caption:
# #   focal_point: Smart

links:
   - icon: open-access
     icon_pack: ai
     name: "Data Descriptor (Scientific Data)"
     url: https://doi.org/10.1038/s41597-025-05330-z
   - icon: zenodo
     icon_pack: ai
     name: "Vol. 1: Grotta di Fumane"
     url: https://doi.org/10.5281/zenodo.6362149
   - icon: zenodo
     icon_pack: ai
     name: "Vol. 2: Grotta di Castelcivita"
     url: https://doi.org/10.5281/zenodo.10631389
   - icon: zenodo
     icon_pack: ai
     name: "Vol. 3: Grotta della Cala"
     url: https://doi.org/10.5281/zenodo.14165189
   - icon: zenodo
     icon_pack: ai
     name: "Vol. 4: Riparo Bombrini"
     url: https://doi.org/10.5281/zenodo.14731694
   - icon: github
     icon_pack: fab
     name: "Research compendium"
     url: https://doi.org/10.5281/zenodo.15131493
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

The Open Aurignacian Project (OAP) digitally preserves lithic assemblages from Italy and makes them openly available for research, teaching, and cultural heritage conservation. To date the project has published **2,016 3D models of stone tools** from four stratified Early Upper Paleolithic sequences, released through four self-standing [**Zenodo**](https://zenodo.org/) repositories under a CC BY 4.0 licence. The 3D models have already underpinned published analyses of core reduction, reduction intensity, and shape variability.

## The four volumes

| Volume | Site | Attribution | Chronology | Models |
|---|---|---|---|---|
| 1 | [Grotta di Fumane](https://doi.org/10.5281/zenodo.6362149) | Protoaurignacian, Aurignacian, Early Gravettian | 41.2–33.2 ky cal BP | 948 |
| 2 | [Grotta di Castelcivita](https://doi.org/10.5281/zenodo.10631389) | Protoaurignacian, Early Aurignacian | 41.8–39.9 ky cal BP | 538 |
| 3 | [Grotta della Cala](https://doi.org/10.5281/zenodo.14165189) | Early Aurignacian | 39.9–37.4 ky cal BP | 420 |
| 4 | [Riparo Bombrini](https://doi.org/10.5281/zenodo.14731694) | Protoaurignacian, Early Aurignacian | 41.2–35.9 ky cal BP | 110 |

The division into four separate repositories ensures proper attribution to the fieldwork and research directors at each site: A. Moroni (Grotta della Cala, Grotta di Castelcivita), M. Peresani (Grotta di Fumane), and F. Negrino and J. Riel-Salvatore (Riparo Bombrini).

## Scanning methodology

Three technologies were used, chosen according to artefact size. The [**Artec Space Spider**](https://www.artec3d.com/portable-3d-scanners/artec-spider) produced most of the meshes (1,250 models) and works well on medium-sized lithics. For small artefacts such as bladelets, where the Spider's resolution falls away, we used micro-computed tomography (571 models) and the [**Artec Micro**](https://www.artec3d.com/portable-3d-scanners/artec-micro) (195 models), which offers the highest resolution of the three.

The step-by-step workflows are published as open protocols:

- [**StyroStone**](https://doi.org/10.17504/protocols.io.4r3l24d9qg1y/v3) — micro-CT and Artec Spider scanning
- [**MicroStone**](https://doi.org/10.17504/protocols.io.81wgb6781lpk/v1) — Artec Micro scanning

## What is in each repository

Every volume contains the 3D meshes in PLY format, a README describing the repository and its metadata, and a CSV file documenting each model. The metadata covers stratigraphic provenience, raw material, technological and typological classification, cortex, preservation, metric data, and full technical detail on each scan — scanner used, polygon count, average edge length, and a resolution score placing each model relative to the rest of the project. Mesh identifiers match those used in previously published studies of the same assemblages, so the 3D data can be joined directly to existing datasets.

For Grotta di Fumane, selected blades and bladelets are also available in WRL format on an [earlier version of the dataset](https://zenodo.org/doi/10.5281/zenodo.7664308).

## What the data can be used for

The repositories support 3D geometric morphometrics, reduction intensity studies on cores and tools, edge-angle analysis of retouched and unretouched blanks, morphometric and technological analysis of cores, machine-learning approaches to lithic classification, and the extraction of outlines for 2D geometric morphometrics. Meshes open in [Meshlab](https://www.meshlab.net/), [CloudCompare](https://www.danielgm.net/cc/), and [Artifact3-D](https://doi.org/10.1371/journal.pone.0268401).

## Updates and citation

The repositories receive new releases as further material is scanned; each DOI above resolves to the "cite all versions" record on Zenodo, so these links always lead to the most current data. Additional sites, including Grotta Paglicci, are planned. This page is updated with new releases and with publications that make use of the datasets.

If you use these data, please cite both the relevant Zenodo repository and the Data Descriptor:

> Falcucci, A., Moroni, A., Negrino, F., Peresani, M. & Riel-Salvatore, J. (2025). The Open Aurignacian Project: 3D scanning and the digital preservation of the Italian Paleolithic record. *Scientific Data* 12, 1037. https://doi.org/10.1038/s41597-025-05330-z

The scanning and technological analyses were supported by the German Research Foundation ([DFG project 431809858](https://gepris.dfg.de/gepris/projekt/431809858?language=en)).
