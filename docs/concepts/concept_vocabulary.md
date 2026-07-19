# Initial Concept Vocabulary for Synthetic Image Detection

## Purpose

This document defines an initial vocabulary of human-understandable visual concepts for interpretable synthetic image detection.

The vocabulary was initially developed as a collection of research hypotheses describing visual characteristics that may distinguish synthetic images from real photographs. A pilot annotation study has since provided preliminary evidence that a subset of these concepts occurs more frequently in synthetic images. However, the pilot dataset is intentionally small and is not sufficient to establish statistical significance, automatic detectability, or generalization across different image generators.

This document therefore serves two purposes:

- to document the complete candidate concept vocabulary considered during the research;
- to identify the subset of concepts selected and validated during the pilot annotation study.

---

# Research Question

> What human-understandable visual concepts should an interpretable synthetic-image detector use?

---

# Initial Candidate Concept Vocabulary

The following table represents the broader candidate vocabulary considered during the exploratory stage of the project. These concepts were identified from the literature on synthetic image artifacts, computer vision, and image forensics.

This vocabulary should **not** be interpreted as the final concept set used by the current prototype.

| Category | Concept | Potentially Detectable? | Why It May Be Useful | Initial Detection Strategy |
|---|---|---:|---|---|
| Human anatomy | Hand anatomy | Yes | Synthetic images may contain unusual finger counts, malformed joints, or implausible hand structures. | Hand detector, pose estimation, vision-language prompts |
| Human anatomy | Facial consistency | Yes | Facial components may show asymmetry, blending artifacts, or inconsistent geometry. | Face landmarks, face embeddings, vision-language prompts |
| Human anatomy | Body proportions | Yes | Limbs and body parts may have implausible sizes, positions, or connections. | Human pose estimation, keypoint analysis |
| Illumination | Lighting consistency | Possibly | Objects within the same scene may appear illuminated from incompatible directions. | Lighting estimation, shadow analysis |
| Illumination | Shadow consistency | Possibly | Shadows may have incorrect direction, softness, shape, or attachment to objects. | Geometry analysis, segmentation |
| Illumination | Reflection consistency | Possibly | Reflections may not correspond correctly to the objects or scene geometry. | Object matching, segmentation |
| Geometry | Perspective consistency | Possibly | Objects may not follow coherent perspective geometry. | Vanishing-point estimation |
| Geometry | Object boundary consistency | Yes | Object edges may merge incorrectly with nearby regions or contain irregular transitions. | Edge detection, segmentation |
| Geometry | Structural coherence | Possibly | Repeated structures or architectural elements may be incomplete or inconsistent. | Structural analysis |
| Texture | Texture smoothness | Yes | Generated regions may appear unnaturally smooth or lack fine details. | Frequency analysis |
| Texture | Repeated texture patterns | Yes | Synthetic images may contain duplicated or unnaturally repeated visual patterns. | Patch similarity |
| Texture | Texture inconsistency | Yes | Texture quality may vary unexpectedly between neighboring regions. | Local feature comparison |
| Text | Text readability | Yes | Generated text may contain malformed, incomplete, or meaningless characters. | OCR |
| Text | Typography consistency | Yes | Letter spacing, font, or orientation may vary unnaturally. | Character-level OCR |
| Background | Background coherence | Possibly | Background regions may contain merged objects or incoherent structures. | Segmentation, object detection |
| Background | Repeated background elements | Yes | Background objects may be duplicated with slight variations. | Patch matching |
| Objects | Object completeness | Yes | Objects may be missing components or contain extra parts. | Object detection |
| Objects | Object interaction | Possibly | Spatial relationships between objects may be physically implausible. | Scene graphs |
| Physics | Physical plausibility | Possibly | Gravity, balance, and support relationships may be inconsistent. | Vision-language reasoning |
| Physics | Material consistency | Possibly | Surface appearance may not match expected material properties. | Material recognition |
| Image quality | Local sharpness inconsistency | Yes | Different image regions may have inconsistent sharpness. | Sharpness analysis |
| Image quality | Noise inconsistency | Yes | Noise patterns may vary unnaturally between regions. | Sensor-noise analysis |
| Image quality | Compression inconsistency | Yes | Different image regions may exhibit incompatible compression traces. | JPEG analysis |
| Semantics | Scene coherence | Possibly | Individually realistic objects may form implausible scenes. | Vision-language models |
| Semantics | Attribute consistency | Possibly | Object attributes may change unexpectedly within the image. | Attribute classifiers |
| Semantics | Counting consistency | Yes | The number of repeated objects or body parts may be incorrect. | Object counting |

---

# Concept Categories

The candidate concepts are grouped into the following categories:

1. Human anatomy
2. Illumination
3. Geometry
4. Texture
5. Text
6. Background
7. Objects
8. Physics
9. Image quality
10. Semantics

---

# Concepts Selected for the Pilot Study

Following the exploratory review, six concepts were selected for the first pilot annotation study.

| Priority | Concept | Reason for Selection |
|---:|---|---|
| 1 | Hand anatomy | Human-understandable and associated with malformed fingers, joints, and hand structures in synthetic images. |
| 2 | Facial consistency | Frequently discussed artifact in generated portraits and suitable for manual annotation. |
| 3 | Text readability | One of the strongest known indicators of image generation artifacts. |
| 4 | Repeated texture patterns | Captures duplicated textures and repetitive local structures. |
| 5 | Object boundary consistency | Detects unrealistic object contours and merging artifacts. |
| 6 | Background coherence | Captures inconsistencies within scene backgrounds and secondary objects. |

These concepts were selected because they are:

- understandable by humans;
- visually assessable;
- reasonably applicable across different image types;
- suitable for future automatic prediction.

---

# Pilot Study Summary

A pilot annotation study was conducted using:

- **10 real images**
- **10 synthetic images**

Each image was manually annotated according to the six selected concepts.

Average concept scores showed substantially higher values for synthetic images than for real images.

| Concept | Real | Synthetic |
|---|---:|---:|
| Hand anatomy | 0.0 | 2.0 |
| Facial consistency | 0.0 | 2.0 |
| Text readability | 0.5 | 3.0 |
| Repeated texture patterns | 0.0 | 1.8 |
| Object boundary consistency | 0.0 | 2.1 |
| Background coherence | 0.0 | 2.1 |

Although the pilot dataset is intentionally small, the results indicate that all six selected concepts exhibit discriminative potential.

Consequently, **all six concepts were retained** for the next stage of the research.

Detailed results are provided in:

```
docs/concepts/pilot_results.md
```

---

# Concept Inclusion Criteria

A concept should remain in the vocabulary only if it satisfies most of the following criteria:

- understandable by non-specialists;
- clearly defined;
- consistently annotatable;
- automatically or semi-automatically predictable;
- useful for distinguishing real and synthetic images;
- generalizable across multiple generators;
- not redundant with another concept;
- capable of supporting meaningful explanations.

---

# Annotation Scale

The pilot study used the following annotation scale.

| Score | Meaning |
|---:|---|
| 0 | The concept is applicable and no visible issue is present |
| 1 | Minor or uncertain issue |
| 2 | Clear issue |
| 3 | Severe issue |
| N/A | Concept cannot be evaluated because the relevant content is absent |

Examples:

- No visible hands → **N/A**
- Visible anatomically correct hands → **0**
- No visible face → **N/A**
- Visible realistic face → **0**
- No visible text → **N/A**
- Clearly readable text → **0**

---

# Concept Validation Questions

Each selected concept should eventually answer the following questions.

1. Can humans annotate the concept consistently?
2. Can the concept be predicted automatically?
3. Is the concept significantly more frequent in synthetic images?
4. Does it improve synthetic-image detection?
5. Does it generalize to unseen image generators?
6. Does it improve model interpretability?
7. Is the concept causally relevant rather than merely correlated?
8. Does it remain useful after controlling for resolution, compression, and image quality?

---

# Methodological Note

The selected concepts should not be interpreted as mandatory indicators of synthetic images.

Modern image generators frequently produce images without obvious visual artifacts. Likewise, real photographs may occasionally contain anomalies due to:

- motion blur;
- image editing;
- compression;
- unusual viewpoints;
- low resolution;
- artistic style;
- naturally uncommon scenes.

Therefore, the concepts should be regarded as explanatory visual factors rather than definitive evidence of image synthesis.

---

# Current Status

The following milestones have been completed.

- ✅ Initial concept vocabulary established.
- ✅ Six concepts selected for the pilot study.
- ✅ Operational concept definitions created.
- ✅ Annotation scale defined.
- ✅ Pilot dataset created (20 images).
- ✅ Manual concept annotation completed.
- ✅ Pilot results analyzed.
- ✅ All six concepts retained.

---

# Next Practical Steps

1. Refine the annotation guidelines with additional examples.
2. Expand the concept-annotated dataset beyond the initial pilot.
3. Include multiple annotators and measure inter-annotator agreement.
4. Investigate automatic concept prediction using conventional computer vision and vision-language models.
5. Evaluate concept robustness across multiple image generators.
6. Control for confounding factors such as compression, resolution, and artistic style.
7. Integrate validated concepts into the first interpretable synthetic image detection model.
