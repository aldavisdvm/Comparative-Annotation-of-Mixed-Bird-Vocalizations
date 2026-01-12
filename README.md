# Comparative Annotation of Mixed Bird Vocalizations Using Raven Lite
## Overview

This repository documents a bioacoustic annotation workflow for manually labeling bird song vocalizations in mixed-species recordings. The project demonstrates how consistent, species-level annotations can be created using Raven Lite and how basic temporal and spectral characteristics can be summarized and compared across multiple species using Python.

The focus is on three commonly co-occurring North American bird species: red-winged blackbirds (Agelaius phoeniceus), marsh wrens (Cistothorus palustris), and northern cardinals (Cardinalis cardinalis). Only clearly identifiable song vocalizations from these target species were included. Call notes, background species, and ambiguous sounds were excluded to maintain annotation clarity and label consistency.

## Dataset Source

All recordings were sourced from xeno-canto.org, a community-curated repository of global bird sound recordings. Recordings were selected to represent mixed acoustic environments in which multiple bird species may be present within a single audio file.

## Annotation Workflow

1. Selected mixed-species bird recordings from xeno-canto.

2. Manually annotated each recording in Raven Lite, identifying complete song vocalizations from the target species only.

3. Exported annotation tables for each recording (required due to varying recording parameters such as sample rate and channel count).

4. Combined all annotation tables into a unified dataset.

5. Computed derived variables from annotation bounds, including:

   * Song duration (seconds)

	* Frequency range (kHz)

6. Generated species-level summary statistics and comparative visualizations to explore temporal and spectral differences across species.

## Annotation Protocol

Song units were annotated by drawing time–frequency bounding boxes around complete vocalizations. Only song vocalizations from the target species were included; calls and non-song vocalizations were excluded. When recordings contained multiple song bouts, each bout was annotated as a separate selection. Distant vocalizations were annotated only when species identity was unambiguous.

## Target Species

Annotations were limited to the following species:

* RWBL — Red-winged Blackbird (Agelaius phoeniceus)

* MAWR — Marsh Wren (Cistothorus palustris)

* NOCA — Northern Cardinal (Cardinalis cardinalis)

Species labels were recorded using standard four-letter species codes in the annotation column.

## Tools and Technologies

* Raven Lite

* Jupyter Notebook

* Python

* NumPy

* Pandas

* Matplotlib

## Raven Lite Configuration

Spectrograms were generated using Raven Lite’s default settings:

* Window type: Hann

* Window size: 512 samples

* Overlap: 50%

* DFT size: automatically determined by Raven Lite

These defaults were used to maintain consistency across all recordings and to reflect typical Raven Lite usage in entry-level bioacoustic annotation workflows.

## Summary of Observations

* Song duration and frequency characteristics differed across species, with partial overlap observed in some features.

* Frequency range plots and scatter visualizations supported the acoustic distinctiveness of species-level labels.

* Variation within species likely reflects natural vocal variability and recording conditions rather than structured biological differences.

## Limitations

* Raven Lite’s fixed spectrogram settings limit fine-tuning of visualization parameters.

* Species representation was uneven across recordings, reflecting real-world variability in mixed acoustic environments.

* Subspecies-level variation and call-type differences were not examined in this project.

## Repository Structure

Data/Annotations_raw/ — CSV files exported from Raven Lite

Data/Annotations_combined/ — Combined and cleaned master annotation files

Figures/ — Selected spectrogram screenshots and generated plots

Notebooks/ — Jupyter notebook for data aggregation, analysis, and visualization
