### File 2: `docs/source-prep-guide.md`

```markdown
# Source Asset Preparation & Grounding Guide

> **Optimizing Documents, Data, and Visual Assets for NotebookLM Multi-Modal Ingestion**

---

## 1. Overview

NotebookLM utilizes grounding algorithms to synthesize uploaded source files into structured outputs. How you prepare, format, and structure your source documents directly dictates how accurately the AI extracts key metrics, concepts, and scene hierarchies.

---

## 2. File-Type Optimization Standards

### A. PDF Documents & Whitepapers
* **Text Layer Verification:** Ensure PDFs contain real vector text layers rather than flat raster images. If using scanned papers, run Optical Character Recognition (OCR) prior to upload.
* **Heading Hierarchy:** Use explicit document tags (`H1`, `H2`, `H3`). NotebookLM uses heading levels to determine scene hierarchy and transition boundaries in video specs.
* **Table Extraction:** Dense visual tables in PDFs can sometimes cause parsing ambiguity. Where possible, convert complex nested tables into clean Markdown tables before exporting to PDF.

### B. Text Files & Markdown (`.md`, `.txt`, `.docx`)
* **Key-Value Annotations:** For high-priority metrics intended for **Hero Data** or **KPI Dashboard** slides, use explicit key-value syntax:
  ```markdown
  Core Metric: 99.4% Uptime
  Primary Bottleneck: Legacy API Latency (420ms)
  Target Milestone: Q3 Production Deployment
Directional Anchor Tags: Insert structural hints directly within your source markdown to signal preferred shot archetypes:

Markdown
[VISUAL: System Architecture Diagram]
The platform operates across three isolated microservice layers...

[TIMELINE: 2024 - 2026]
Phase 1 launched in Q1 2024, followed by global rollouts...
C. Visual Assets & Diagrams (.png, .jpg, .webp)
Resolution & Aspect Ratio: Upload images at a minimum of 1080p. Preferred canvas geometry is 16:9 (1920x1080) to match native video output.

Descriptive File Naming: Avoid generic camera file names (e.g., DCIM_00412.jpg). Rename files semantically so the multi-modal engine can reference them during synthesis:

❌ IMG_9821.png

✅ architecture_cloud_layer_diagram.png

UI High-Contrast Framing: Technical screenshots or UI wireframes should have crisp borders and high-contrast text against their backgrounds for precise spatial interpretation.

3. Multi-Document Grounding Strategy
When binding multiple disparate source files into a single notebook (e.g., a PDF technical specification + an audio transcript + an architectural image):

┌─────────────────────────────────────────────────────────────────────────┐
│                       MULTI-SOURCE GROUNDING MAP                        │
├─────────────────────────────────────────────────────────────────────────┤
│ Technical Whitepaper (PDF) ──> Feeds Data Metrics & Telemetry Shots     │
│ Audio Transcript (.txt)    ──> Feeds Executive Quotes & Statement Shots │
│ System Architecture (.png) ──> Feeds Visual Hero & Diagram Splits       │
└─────────────────────────────────────────────────────────────────────────┘
Multi-Source Directorial Prompt Example:
"Synthesize the uploaded PDF technical specification and the audio interview transcript into an 8-scene video deck. Map all performance metrics from the PDF to the Telemetry KPI Dashboard archetype, and use quotes from the transcript for the Executive Statement scenes."
