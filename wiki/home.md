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

- [100% report](../rapport/100_percent_amir_jacobs.pdf)

## Main Deliverables

- [Report folder](../rapport) - report outputs and supporting material.
- [Code folder](../code) - notebooks and dependency list for the prototype work.
- [Research overview](Research.md) overview of research documents and choices made.
- [Planning and progress](../rapport/research/planning.md) - project planning and progress notes.
- [GenAI use documentation](../rapport/research/genai.md) - prompts and examples of GenAI-supported work.
- [Image stability check](Image-Embedding-Stability.md) a check on how stable cosine similarity is on validation for each CNN model.

## Code and Notebook Order

The code material is organised as a small notebook sequence:

1. [Dataset split](../code/01_split_dataset.ipynb) - creates the train, validation, and test split at fabric level.
2. [Data exploration](../code/02_data_exploration.ipynb) - summarises the prepared split and produces dataset figures.
3. [Measurement-count distribution analysis](../code/03_measurement_count_distribution_analysis.ipynb) - documents measurement availability per fabric sample and split.
4. [Frozen CNN image classifier](../code/04_train_frozen_cnn_image_classifier.ipynb) - trains and evaluates the image classifier used in the first prototype.
5. [CNN embedding similarity check](../code/05_cnn_embedding_similarity_check.ipynb) - checks whether same-class image embeddings are closer than different-class embeddings.
6. [Fine-tuned CNN image classifier](../code/06_train_finetuned_cnn_image_classifier.ipynb) - fine-tunes the final DenseNet201 block for the second image-model iteration.
7. [CNN explainability heatmaps](../code/07_cnn_explainability_heatmaps.ipynb) - generates Grad-CAM heatmaps for selected validation images.
8. [Test-representation similarity analysis](../code/08_test_representation_similarity_analysis.ipynb) - compares image and spectra representation similarities.
9. [Scalability test](../code/09_scalability_test_second_iteration.ipynb) - measures model-only inference time as the number of validation images increases.
10. [Final test evaluation](../code/10_final_test_evaluation_second_iteration.ipynb) - evaluates the selected second-iteration system on the locked held-out test split.

Dependencies are listed in [code/requirements.txt](../code/requirements.txt).
