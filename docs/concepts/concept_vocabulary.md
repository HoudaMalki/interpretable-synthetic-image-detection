# Initial Concept Vocabulary for Synthetic Image Detection

## Purpose

This document defines an initial vocabulary of human-understandable visual concepts that may be useful for detecting AI-generated images.

At this stage, the concepts are research hypotheses rather than confirmed indicators. Each concept must later be tested experimentally to determine:

- whether it can be detected reliably,
- whether it contributes to synthetic-image detection,
- whether it generalizes across image generators,
- and whether it produces explanations that are useful to humans.

## Research Question

> What human-understandable visual concepts should an interpretable synthetic-image detector use?

## Initial Concept Vocabulary

| Category | Concept | Potentially Detectable? | Why It May Be Useful | Initial Detection Strategy |
|---|---|---:|---|---|
| Human anatomy | Hand anatomy | Yes | Synthetic images may contain unusual finger counts, malformed joints, or implausible hand structures. | Hand detector, pose estimation, vision-language prompts |
| Human anatomy | Facial consistency | Yes | Facial components may show asymmetry, blending artifacts, or inconsistent geometry. | Face landmarks, face embeddings, vision-language prompts |
| Human anatomy | Body proportions | Yes | Limbs and body parts may have implausible sizes, positions, or connections. | Human pose estimation, keypoint analysis |
| Illumination | Lighting consistency | Possibly | Objects within the same scene may appear to be illuminated from incompatible directions. | Lighting estimation, shadow analysis, vision-language prompts |
| Illumination | Shadow consistency | Possibly | Shadows may have incorrect direction, softness, shape, or attachment to objects. | Segmentation, geometry analysis, vision-language prompts |
| Illumination | Reflection consistency | Possibly | Reflections may not correspond correctly to the objects or scene geometry. | Object matching, segmentation, multimodal reasoning |
| Geometry | Perspective consistency | Possibly | Objects may not follow a coherent perspective or vanishing-point structure. | Line detection, vanishing-point estimation |
| Geometry | Object boundary consistency | Yes | Object edges may merge incorrectly with nearby regions or contain irregular transitions. | Edge detection, segmentation, local feature analysis |
| Geometry | Structural coherence | Possibly | Repeated structures, architecture, or object components may be incomplete or geometrically inconsistent. | Object detection, structural analysis, vision-language prompts |
| Texture | Texture smoothness | Yes | Some generated regions may appear over-smoothed or lack natural high-frequency detail. | Frequency analysis, local texture descriptors |
| Texture | Repeated texture patterns | Yes | Synthetic images may contain duplicated or unnaturally repeated visual patterns. | Patch similarity, autocorrelation, feature matching |
| Texture | Texture inconsistency | Yes | Texture quality may vary unexpectedly across neighboring regions or similar objects. | Local feature comparison, frequency analysis |
| Text | Text readability | Yes | Text inside generated images may contain malformed, incomplete, or meaningless characters. | Optical character recognition, language-model validation |
| Text | Typography consistency | Yes | Letter size, spacing, orientation, or font style may vary unnaturally. | OCR bounding boxes, character-level analysis |
| Background | Background coherence | Possibly | Background regions may include merged objects, incomplete structures, or incoherent details. | Segmentation, object detection, vision-language prompts |
| Background | Repeated background elements | Yes | Similar objects or patterns may be duplicated with unusual variations. | Image retrieval features, patch matching |
| Objects | Object completeness | Yes | Objects may be missing components or contain extra parts. | Object detection, part-based models, vision-language prompts |
| Objects | Object interaction | Possibly | Contact and spatial relationships between objects may be physically implausible. | Scene graphs, relationship detection |
| Physics | Physical plausibility | Possibly | Gravity, support, balance, and material behavior may be inconsistent. | Vision-language reasoning, scene understanding |
| Physics | Material consistency | Possibly | Surfaces may not reflect expected properties of metal, glass, skin, fabric, or water. | Material recognition, reflectance analysis |
| Image quality | Local sharpness inconsistency | Yes | Some image regions may be unusually sharp while adjacent regions are blurred or poorly defined. | Local sharpness measures, frequency analysis |
| Image quality | Noise inconsistency | Yes | Noise patterns may differ unnaturally between regions of the same image. | Sensor-noise analysis, residual analysis |
| Image quality | Compression inconsistency | Yes | Different image regions may show incompatible compression or resampling traces. | Forensic residuals, JPEG analysis |
| Semantics | Scene coherence | Possibly | Objects may individually appear realistic but form an implausible or contradictory scene. | Vision-language models, scene graphs |
| Semantics | Attribute consistency | Possibly | Object color, shape, material, or identity may change unexpectedly across the image. | Object embeddings, attribute classifiers |
| Semantics | Counting consistency | Yes | The number of repeated objects or body parts may be incorrect or ambiguous. | Object detection, counting models |

## Proposed Concept Categories

The initial concepts are grouped into the following categories:

1. Human anatomy
2. Illumination
3. Geometry
4. Texture
5. Text
6. Background
7. Objects
8. Physics
9. Image quality
10. Semantic coherence

## Recommended Concepts for the First Prototype

The first prototype should begin with a small and manageable subset rather than using the complete vocabulary.

The proposed initial concepts are:

| Priority | Concept | Reason for Selection |
|---:|---|---|
| 1 | Text readability | Can be evaluated using OCR and character-level measurements. |
| 2 | Hand anatomy | Human-understandable and commonly discussed in synthetic-image analysis. |
| 3 | Facial consistency | Relevant to images containing people and supported by existing face-analysis tools. |
| 4 | Repeated texture patterns | Can be investigated using patch-level similarity measures. |
| 5 | Local sharpness inconsistency | Can be measured using conventional image-processing techniques. |
| 6 | Object boundary consistency | Can be studied using edges and segmentation masks. |
| 7 | Background coherence | Relevant to complex generated scenes and suitable for vision-language evaluation. |
| 8 | Perspective consistency | Provides a geometry-based concept distinct from semantic concepts. |

## Concept Inclusion Criteria

A concept should be retained in the vocabulary only if it satisfies most of the following criteria:

- It is understandable to a non-specialist.
- It can be defined clearly.
- It can be annotated consistently.
- It can be estimated automatically or semi-automatically.
- It contributes useful information for real-versus-synthetic classification.
- It generalizes across multiple generators.
- It is not merely a duplicate of another concept.
- It supports a meaningful explanation of the final prediction.

## Concept Validation Questions

For each concept, the following questions must be investigated:

1. Can humans annotate the concept consistently?
2. Can the concept be predicted automatically?
3. Is the concept more frequent in synthetic images than in real images?
4. Does the concept improve detection performance?
5. Does the concept generalize to unseen generators?
6. Is the concept useful for explaining individual predictions?
7. Is the concept causally relevant, or merely correlated with the dataset?
8. Does the concept remain useful after controlling for image resolution and compression?

## Proposed Annotation Scale

Each image-concept pair may initially be annotated using a simple ordinal scale:

| Score | Meaning |
|---:|---|
| 0 | Concept is not present or no inconsistency is visible |
| 1 | Weak or uncertain evidence |
| 2 | Moderate evidence |
| 3 | Strong and clearly visible evidence |
| N/A | Concept cannot be evaluated in this image |

Examples:

- Hand anatomy should be marked `N/A` when no hands are visible.
- Text readability should be marked `N/A` when the image contains no text.
- Facial consistency should be marked `N/A` when no face is visible.

## Important Methodological Note

The concept vocabulary must not assume that every synthetic image contains visible artifacts.

Modern generators can produce images without obvious anatomical, textural, or geometric errors. Therefore, the vocabulary should be treated as a set of candidate explanatory factors rather than a fixed checklist for identifying synthetic images.

The experiments must also determine whether some concepts occur in real images because of:

- motion blur,
- image editing,
- compression,
- unusual camera angles,
- low resolution,
- artistic style,
- or naturally uncommon scenes.

## Next Practical Steps

1. Review the initial vocabulary with the supervisor.
2. Reduce the vocabulary to approximately 5–10 concepts for the first prototype.
3. Write a precise operational definition for each selected concept.
4. Create positive, negative, and ambiguous examples.
5. Design an annotation form.
6. Annotate a small pilot dataset.
7. Measure agreement between annotators.
8. Test automatic concept extraction using CLIP prompts and conventional vision tools.
9. Evaluate whether concept scores differ between real and synthetic images.
10. Use the validated concepts in the first concept-based model.
