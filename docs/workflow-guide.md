# Director-Level Workflow & System Architecture Guide

> **Technical Execution Protocols for NotebookLM & Gemini Generative Video Engines**

---

## 1. Architectural Foundations

Generative visual engines require structured boundaries to prevent generic output defaults (e.g., standard stock imagery, soft drop shadows, or uninspired corporate templates). The specifications in this repository act as **deterministic design systems** that enforce strict visual, spatial, motion, and acoustic parameters across five distinct layers:

┌─────────────────────────────────────────────────────────────────────────┐
│                       5-LAYER SPECIFICATION MATRIX                      │
├─────────────────────────────────────────────────────────────────────────┤
│ 1. VISUAL IDENTITY & LIGHTING  ──> Hex palettes, volumetric grading     │
│ 2. TYPOGRAPHIC SYSTEM         ──> Scale jump ratios, tracking, mono     │
│ 3. CAMERA MOTION & PACING     ──> Lens focal lengths, editing rhythm   │
│ 4. AUDIO & ATMOSPHERIC SOUND   ──> Soundscapes, music cues, Foley FX    │
│ 5. MODULAR SHOT CATALOG        ──> Archetypal layouts & scene structures │
└─────────────────────────────────────────────────────────────────────────┘


---

## 2. Core Directorial Principles

When executing prompts or building custom YAML specifications, adhere to these three director-level rules:

### A. Specificity Over Adjectives
Avoid subjective, ambiguous descriptors such as `"futuristic"`, `"sleek"`, or `"make it look cool"`. Replace them with explicit structural metrics:
* ❌ *Bad:* `"A sleek dark interface with glowing green buttons."`
* ✅ *Good:* `"Dark slate canvas (#090D16) framed by 1px slate borders (#1E293B). Primary action elements use terminal green (#00FF66) with CRT scanline textures."`

### B. Luminance & Contrast Enforcement
Video decks are viewed across varying screen resolutions and lighting environments. Enforce minimum contrast thresholds by strictly pairing light foreground elements with dark background voids, or vice versa:
* **High-Luminance Accents:** `#00FF66` (Terminal Green), `#FACC15` (Amber Yellow), `#00F0FF` (Cyan Glow)
* **Low-Luminance Canvas:** `#030712` (Cosmic Void), `#090D16` (Dark Slate), `#000000` (Pure Pitch Black)

### C. The Language Mirror Protocol
To preserve structural geometry when generating presentations in non-English languages (e.g., Japanese, German, Spanish, French), typography rules must decouple **layout tracking** from **body rendering**:
```yaml
Typography System:
  Headings:
    Font: "Monospaced Geometric Sans"
    Tracking: "Wide (0.15em spacing)"
  Body:
    Font: "Clean Tech Sans"
    Language Directives: "Dynamically render body text in the user's requested language while maintaining strict 1.6x line-height."
3. End-to-End Execution Workflow
┌─────────────────┐      ┌──────────────────┐      ┌───────────────────┐      ┌──────────────────┐
│ 1. SELECT SPEC  │ ───> │ 2. BIND SOURCES  │ ───> │ 3. INJECT RULES   │ ───> │ 4. PROMPT DECK   │
│  (Pick .yaml)   │      │  (PDFs, Docs)    │      │ (Custom Inst.)    │      │  (Issue Cmd)     │
└─────────────────┘      └──────────────────┘      └───────────────────┘      └──────────────────┘
Select a Specification: Choose an archetype file from specs/ that matches your target mood (e.g., specs/04_cyberpunk_hacker.yaml for technical infrastructure, or specs/08_corporate_tech_launch.yaml for product keynotes).

Bind Source Materials: Upload your source documents, PDFs, or notes to NotebookLM's Sources panel.

Inject System Instructions: Copy the entire YAML block from your chosen specification file and paste it into NotebookLM's Custom Instructions box (located under Chat Settings).

Issue the Directorial Directive: Run a structured generation query:

"Using the uploaded source materials, generate an 8-scene cinematic video deck detailing [TOPIC]. Strictly adhere to the loaded YAML specification for color palette, shot catalog types, pacing, and audio cues."

4. Single-Slide Revision & Iteration Protocols
If an individual slide or scene deviates from the target design system during generation, use isolated surgical prompts rather than re-rolling the entire deck:

To Shift Layout Archetype:

"Refactor Scene 4 to use the Telemetry KPI Dashboard layout archetype from the loaded spec."

To Enforce Contrast:

"Increase the scale contrast in Scene 2. Make the primary metric 3x larger in terminal green (#00FF66) against a pure black card (#000000)."

To Adjust Editing Pacing:

"Adjust camera instructions for Scene 6 from a snap zoom to a slow 6-second continuous orbital drift."
