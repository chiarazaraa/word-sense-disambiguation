# Word Sense Disambiguation

## Project Overview
This project explores Word Sense Disambiguation (WSD) using a semi-supervised Yarowsky-style bootstrapping approach.

The objective is to assign the correct sense to ambiguous words based on their local context. The project combines corpus preprocessing, collocational feature extraction, decision-list style rules, and iterative self-labeling.

---

## Objective
The goal of the project is to simulate a word sense disambiguation setting and evaluate whether a bootstrapping approach can successfully distinguish between different senses of ambiguous terms.

In particular, the notebook:
- preprocesses a text corpus
- creates synthetic ambiguous targets
- extracts local contextual features
- applies a Yarowsky-inspired bootstrapping procedure
- evaluates prediction quality in terms of accuracy and coverage

---

## Methodology

### 1. Corpus preprocessing
The text corpus is cleaned and segmented into sentences using standard NLP preprocessing steps:
- lowercasing
- removal of markup
- sentence tokenization
- word tokenization

### 2. Synthetic ambiguity generation
Pairs of words are merged into synthetic ambiguous targets in order to simulate a controlled WSD setting.

Examples:
- `carspeech` → car / speech
- `treeviolence` → tree / violence
- `chairpaper` → chair / paper

### 3. Feature extraction
For each ambiguous target, the model extracts collocational features from a local context window around the word occurrence.

### 4. Bootstrapping
A Yarowsky-style semi-supervised procedure is applied:
- initialize with seed words
- build feature statistics
- compute decision rules using log-likelihood ratios
- label new examples iteratively
- stop when growth becomes small

### 5. Discourse-level adjustment
The project also applies a simplified one sense per discourse strategy to improve consistency across nearby examples.

---

## Evaluation
The model is evaluated automatically against a synthetic gold standard using:
- accuracy
- coverage
- token-level evaluation
- sentence-level evaluation

---

## Repository Contents
- `Word_Sense_Disambiguation.ipynb`: main notebook with the full analysis
- `report.pdf`: project report
- `README.md`: project description

---


## Author
Project developed as part of university coursework in Natural Language Processing.
