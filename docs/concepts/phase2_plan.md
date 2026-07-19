# Phase 2 — Concept Learning Plan

## Objective

The objective of this phase is to identify, define, annotate, and validate human-understandable concepts that may support interpretable synthetic-image detection.

This phase does not yet aim to build the final detector.

## Phase 2 Outputs

The expected outputs are:

- an initial concept vocabulary,
- a reduced concept set for the first prototype,
- operational definitions for each concept,
- an annotation protocol,
- a small concept-labeled pilot dataset,
- an analysis of concept relevance,
- and recommendations for the first concept-based model.

## Task 1 — Review the Concept Vocabulary

Review the candidate concepts and classify each one as:

- retain,
- revise,
- combine,
- postpone,
- or remove.

## Task 2 — Select the First Concepts

Select approximately 5–10 concepts according to:

- interpretability,
- detectability,
- annotation feasibility,
- expected relevance,
- and diversity across concept categories.

## Task 3 — Define Each Concept

For every selected concept, document:

- definition,
- inclusion criteria,
- exclusion criteria,
- positive examples,
- negative examples,
- ambiguous examples,
- annotation scale,
- and possible automatic detection method.

## Task 4 — Select a Pilot Dataset

Create a balanced pilot dataset containing:

- real images,
- synthetic images,
- images from multiple generators,
- images with and without people,
- images with and without text,
- and a range of scene types.

The pilot should initially remain small enough for manual inspection.

## Task 5 — Annotate the Pilot Dataset

Annotate each applicable concept using the scale:

- 0: absent,
- 1: weak,
- 2: moderate,
- 3: strong,
- N/A: not applicable.

## Task 6 — Validate the Annotations

Evaluate:

- annotation consistency,
- ambiguous concepts,
- concept frequency,
- concept co-occurrence,
- and differences between real and synthetic images.

## Task 7 — Test Automatic Concept Extraction

Test at least two approaches:

1. CLIP-based text prompts.
2. Conventional computer-vision or forensic measurements.

## Task 8 — Decide Which Concepts Enter the Prototype

Retain concepts that are:

- understandable,
- measurable,
- sufficiently frequent,
- discriminative,
- and useful for explanations.

## Completion Criteria

Phase 2 will be considered complete when:

- the initial vocabulary has been reviewed,
- 5–10 concepts have been selected,
- each selected concept has an operational definition,
- a pilot dataset has been annotated,
- initial concept statistics have been calculated,
- and a final concept subset has been selected for the first prototype.
