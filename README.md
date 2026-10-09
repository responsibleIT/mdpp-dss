# Molecular Digital Product Passport: An AI-Supported Decision System for Textile Characterisation

**Student:** Amir Jacobs  
**Applied AI Lab:** Responsible AI  
**Lab supervisors:** Marcio Fuckner, Martijn de Bruin  
**Lecturer supervisor:** David van Dijk  
**Period:** Semester 2, academic year 2025-2026  
**Portfolio stage:** 100% Go/No-Go  
**Last updated:** 12 June 2026

---

## Project Overview

This repository contains the portfolio material for my graduation research. The project investigates an AI-supported decision system for textile characterisation in the context of molecular digital product passports.

## Current Portfolio Stage

The current primary deliverable is the 100% report:

- [100% report](./rapport/100_percent_amir_jacobs.pdf)

## Main Deliverables

- [Report folder](./rapport/) - the final thesis and supporting research material.
- [Code folder](./code/) - notebooks and dependency list for the prototype work.
- [Research notes](./rapport/research/) - source notes, design notes, diagrams, and process documentation.
- [Portfolio wiki](./wiki/home.md) - the portfolio wiki pages, exported to Markdown (listed below).
- [Research summary](./wiki/Research.md) - summary of the research done alongside the thesis.
- [Planning and progress](./rapport/research/planning.md) - project planning and progress notes.
- [GenAI use documentation](./rapport/research/genai.md) - prompts and examples of GenAI-supported work.
- [Image embedding stability](./wiki/Image-Embedding-Stability.md) - test to see how stable image embeddings from the CNN are under slight variations.

## Code and Notebook Order

The code material is organised as a small notebook sequence:

1. [Dataset split](./code/01_split_dataset.ipynb) - creates the train, validation, and test split at fabric level.
2. [Data exploration](./code/02_data_exploration.ipynb) - summarises the prepared split and produces dataset figures.
3. [Measurement-count distribution analysis](./code/03_measurement_count_distribution_analysis.ipynb) - documents measurement availability per fabric sample and split.
4. [Frozen CNN image classifier](./code/04_train_frozen_cnn_image_classifier.ipynb) - trains and evaluates the image classifier used in the first prototype.
5. [CNN embedding similarity check](./code/05_cnn_embedding_similarity_check.ipynb) - checks whether same-class image embeddings are closer than different-class embeddings.
6. [Fine-tuned CNN image classifier](./code/06_train_finetuned_cnn_image_classifier.ipynb) - fine-tunes the final DenseNet201 block for the second image-model iteration.
7. [CNN explainability heatmaps](./code/07_cnn_explainability_heatmaps.ipynb) - generates Grad-CAM heatmaps for selected validation images.
8. [Test-representation similarity analysis](./code/08_test_representation_similarity_analysis.ipynb) - compares image and spectra representation similarities.
9. [Scalability test](./code/09_scalability_test_second_iteration.ipynb) - measures model-only inference time as the number of validation images increases.
10. [Final test evaluation](./code/10_final_test_evaluation_second_iteration.ipynb) - evaluates the selected second-iteration system on the locked held-out test split.

Dependencies are listed in [code/requirements.txt](./code/requirements.txt).

## Getting the NIR-SORT Dataset

The notebooks use the NIR-SORT dataset, a public NIST release of NIR spectra and microscopy images of origin-defined and real-world textiles. The dataset is **not** included in this repository because of its size.

| | |
|---|---|
| **Title** | Near Infrared Spectra of Origin-defined and Real-world Textiles (NIR-SORT) |
| **Publisher** | National Institute of Standards and Technology (NIST), version 2.0.1 |
| **DOI** | [10.18434/mds2-3325](https://doi.org/10.18434/mds2-3325) |
| **Download** | [NIST Public Data Repository](https://data.nist.gov/od/id/mds2-3325) (free, no registration) |
| **Mirror** | [Materials Data Facility, 10.18126/61v0-rf98](https://doi.org/10.18126/61v0-rf98) |
| **License** | [NIST open data / public domain](https://www.nist.gov/open/license) |
| **Contact** | Katarina Goodge (katarina.goodge@nist.gov) |

The release contains 113 fabrics: benchtop and handheld NIR spectra (about 4,248 files, about 193 MB) and optical microscopy images (about 1,044 files, about 10.6 GB). The specimen files are zipped per source directory, so download and extract the `Spectroscopy/` and `Microscopy/` trees. After extraction, the raw dataset root should contain `README_main.txt`, `Microscopy/`, `Spectroscopy/`, and `full_dataset_composition_matrix.csv`.

`01_split_dataset.ipynb` looks for that folder automatically from the notebook working directory. Set `RAW_DATASET_ROOT_OVERRIDE` in the first cell if the auto-detection does not find the extracted dataset.

## Research Notes and Process Documentation

The research folder contains Markdown notes and diagrams used during the project. These files document background research, design decisions, prototype flows, and supporting material for the report. The portfolio wiki pages (research summary and the image-embedding stability check) are exported to the [`wiki/`](./wiki/) folder.
