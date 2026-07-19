# Phase 2 – Concept Learning Plan

## Objective

The objective of this phase is to identify, define, annotate, and validate human-understandable visual concepts that support interpretable synthetic image detection.

This phase focuses on establishing a reliable concept vocabulary and annotation methodology before developing the final concept-based detection model.

---

# Phase 2 Outputs

The expected outputs of this phase are:

- an initial concept vocabulary;
- a selected subset of concepts for the first prototype;
- operational concept definitions;
- an annotation protocol;
- a manually annotated pilot dataset;
- an analysis of concept relevance; and
- recommendations for the first interpretable model.

---

# Task 1 – Review the Concept Vocabulary ✅

Review candidate concepts from the literature and organize them into a structured vocabulary.

### Outcome

- Initial concept vocabulary established.
- Candidate concepts grouped into semantic categories.
- Vocabulary documented in `docs/concepts/concept_vocabulary.md`.

---

# Task 2 – Select the First Concepts ✅

Select a manageable subset of concepts according to:

- interpretability;
- annotation feasibility;
- expected usefulness;
- diversity across concept categories; and
- potential for future automatic prediction.

### Selected Concepts

- Hand anatomy
- Facial consistency
- Text readability
- Repeated texture patterns
- Object boundary consistency
- Background coherence

---

# Task 3 – Define Each Concept ✅

For every selected concept, document:

- definition;
- inclusion criteria;
- exclusion criteria;
- annotation scale;
- annotation notes; and
- potential automatic detection methods.

### Outcome

Operational concept definitions documented in:

`docs/concepts/concept_definitions.md`

---

# Task 4 – Create the Pilot Dataset ✅

Construct a balanced pilot dataset suitable for manual annotation.

### Dataset

- 10 real images
- 10 synthetic images

Images were selected from the Synthbuster benchmark and include diverse scene content.

---

# Task 5 – Annotate the Pilot Dataset ✅

Manually annotate each applicable concept using the following scale.

| Score | Meaning |
|---:|---|
| 0 | No visible issue |
| 1 | Minor issue |
| 2 | Clear issue |
| 3 | Severe issue |
| N/A | Concept not applicable |

### Outcome

Pilot annotations stored in:

`data/concepts/pilot_annotations.csv`

---

# Task 6 – Validate the Pilot Annotations ✅

Evaluate:

- applicability of each concept;
- differences between real and synthetic images;
- annotation practicality; and
- usefulness of each concept.

### Outcome

The pilot study demonstrated higher average concept scores for synthetic images across all six selected concepts.

All six concepts were retained for the next stage.

Detailed analysis is available in:

`docs/concepts/pilot_results.md`

---

# Task 7 – Investigate Automatic Concept Prediction 🔄

Investigate methods for predicting concept values automatically.

Potential approaches include:

1. CLIP-based vision-language prompts.
2. Conventional computer vision techniques.
3. Lightweight concept classifiers.

This task will continue during the implementation of the interpretable detection model.

---

# Task 8 – Prepare the Concept-Based Prototype 🔄

Use the validated concepts to design the first interpretable synthetic image detector.

Future work includes:

- expanding the concept-annotated dataset;
- measuring inter-annotator agreement;
- training automatic concept predictors;
- integrating concept predictions into the detection pipeline; and
- evaluating interpretability and detection performance.

---

# Phase 2 Status

| Task | Status |
|---|:---:|
| Review concept vocabulary | ✅ |
| Select pilot concepts | ✅ |
| Define concepts | ✅ |
| Create pilot dataset | ✅ |
| Annotate pilot dataset | ✅ |
| Validate pilot results | ✅ |
| Investigate automatic concept prediction | 🔄 |
| Prepare concept-based prototype | 🔄 |

---

# Deliverables

The following deliverables have been completed during Phase 2.

- `docs/concepts/concept_vocabulary.md`
- `docs/concepts/concept_definitions.md`
- `docs/concepts/pilot_results.md`
- `data/concepts/pilot_annotations.csv`

The remaining work will focus on scaling the annotation effort and implementing automatic concept prediction as part of the interpretable synthetic image detection model.
