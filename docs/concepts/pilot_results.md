# Phase 2 – Pilot Concept Annotation Results

## Overview

This pilot study was conducted to evaluate whether a set of manually defined visual concepts can effectively distinguish real images from synthetic images before developing an interpretable synthetic image detection model.

The objectives of the pilot were to:

- validate the proposed concept definitions;
- assess whether the concepts are consistently applicable;
- identify concepts that discriminate between real and synthetic images;
- establish a methodology for creating a larger concept-annotated dataset.

## Pilot Dataset

The pilot dataset consists of **20 images**:

| Class | Images |
|-------|-------:|
| Real | 10 |
| Synthetic | 10 |
| Total | 20 |

Real images were selected from the **Synthbuster RAISE-1K** subset.

Synthetic images were selected from the **Synthbuster** benchmark.

## Annotation Procedure

Each image was manually inspected and annotated according to six predefined visual concepts.

The following annotation scale was used:

| Score | Meaning |
|------:|---------|
| 0 | No visible issue |
| 1 | Minor issue |
| 2 | Clear issue |
| 3 | Severe issue |
| N/A | Concept not applicable |

Annotations were performed manually by the project author.

## Evaluated Concepts

1. Hand anatomy
2. Facial consistency
3. Text readability
4. Repeated texture patterns
5. Object boundary consistency
6. Background coherence

## Pilot Results

Average concept scores are shown below, excluding N/A values.

| Concept | Real | Synthetic |
|---------|-----:|----------:|
| Hand anatomy | 0.0 | 2.0 |
| Facial consistency | 0.0 | 2.0 |
| Text readability | 0.5 | 3.0 |
| Repeated texture patterns | 0.0 | 1.8 |
| Object boundary consistency | 0.0 | 2.1 |
| Background coherence | 0.0 | 2.1 |

## Discussion

The pilot annotations indicate that all six concepts exhibit higher average scores for synthetic images than for real images.

Particularly strong indicators include:

- text readability;
- object boundary consistency;
- background coherence;
- hand anatomy;
- facial consistency.

Repeated texture patterns also demonstrated discriminative potential, although with a slightly lower average score.

The pilot confirmed that the annotation protocol is practical and that the concepts can be applied across different image types.

## Decision

Based on the pilot study, all six concepts will be retained for the next stage of the research.

The next step is to expand the concept annotations to a larger subset of images to support the development of an interpretable synthetic image detection model.

## Limitations

The pilot dataset contains only twenty images and therefore cannot be considered statistically representative.

Its purpose is to validate the annotation methodology rather than evaluate model performance.

A larger concept-annotated dataset will be created during the subsequent phase of the project.

## Conclusion

The pilot study demonstrated that manually defined visual concepts can distinguish real and synthetic images at a qualitative level.

The annotation protocol, concept definitions, and scoring methodology established in this phase provide the foundation for the larger concept annotation effort and the interpretable learning framework developed in the following stages of this research.
