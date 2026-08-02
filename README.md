# NotebookLM Studio — Cinematic Video Specification Suite

> **Production-Ready Prompt Engine & System Architecture for Director-Level Generative Presentations**

[![YAML Validation](https://github.com/your-username/notebooklm-cinematic-suite/actions/workflows/ci.yml/badge.svg)](https://github.com/your-username/notebooklm-cinematic-suite/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Specs Count](https://img.shields.io/badge/specs-9%20Production%20Ready-blue.svg)](#-catalog-of-production-specs)
[![Platform](https://img.shields.io/badge/Platform-NotebookLM%20%2F%20Gemini-purple.svg)](https://notebooklm.google.com)

NotebookLM’s video generation engine renders structured textual specifications into high-impact visual presentations. This repository provides 9 production-ready, genre-defined YAML specifications designed to establish strict boundaries across five architectural layers.

---

## 🖼 Showcase & Output Artifacts

Here is an example of applying **Spec #04 (High-Tech Cyberpunk)** to a raw technical whitepaper:

| Raw Document Source | Rendered Frame Output (Spec #04) |
| :--- | :--- |
| **Input:** Dense markdown whitepaper on microservice architecture & latency bottlenecks. | **Output:** 16:9 dark slate canvas, terminal green (`#00FF66`) typography, telemetry split grid, and CRT scanline overlay. |

> 📁 *For full exported PDF decks and high-res sample artifacts, see the [`/assets/examples/`](assets/examples/) directory.*

---

## ⚡ Execution Protocol

1. **Choose a Spec:** Browse the catalog below and open your desired `.yaml` file in [`/specs`](specs/).
2. **Deploy System Instructions:** Copy the raw YAML content into the **Custom Instructions** or prompt box in NotebookLM.
3. **Bind Source Materials:** Upload your source documents, research papers, scripts, or notes into NotebookLM.
4. **Execute Video Directives:** Prompt NotebookLM with your target topic, specifying slide count and preferred language:
   > *"Generate an 8-scene Video Spec on Quantum Computing using Spec #04 High-Tech Cyberpunk."*

---

## 🎬 Catalog of Production Specs

| # | Spec Name & File | Style & Visual Aesthetic | Primary Palette |
| :-: | :--- | :--- | :--- |
| **01** | [`01_scifi_deepspace.yaml`](specs/01_scifi_deepspace.yaml) | Epic Hard Sci-Fi / Interstellar Cosmic Realism | `#030712` (Void) / `#06B6D4` (Cyan) |
| **02** | [`02_dark_fantasy.yaml`](specs/02_dark_fantasy.yaml) | Gothic Renaissance / Dark Mythic Realism | `#0C0A09` (Obsidian) / `#991B1B` (Crimson) |
| **03** | [`03_neo_noir.yaml`](specs/03_neo_noir.yaml) | Neo-Noir / High-Contrast Crime Editorial | `#000000` (Black) / `#FACC15` (Amber) |
| **04** | [`04_cyberpunk_hacker.yaml`](specs/04_cyberpunk_hacker.yaml) | Cyber-Industrial / Developer HUD Interface | `#090D16` (Slate) / `#00FF66` (Terminal Green) |
| **05** | [`05_synthwave_retro.yaml`](specs/05_synthwave_retro.yaml) | 1980s Neon Futurism / Outrun Arcade Editorial | `#110928` (Purple) / `#FF007F` (Hot Pink) |
| **06** | [`06_nature_documentary.yaml`](specs/06_nature_documentary.yaml) | Environmental Realism / National Geographic Style | `#0F172A` (Ocean) / `#22C55E` (Forest Green) |
| **07** | [`07_vintage_silent_film.yaml`](specs/07_vintage_silent_film.yaml) | 1920s Art Deco Intertitle & Silent Cinema | `#121212` (Velvet) / `#D4AF37` (Deco Gold) |
| **08** | [`08_corporate_tech_launch.yaml`](specs/08_corporate_tech_launch.yaml) | Silicon Valley Keynote / Modern Minimalist | `#F8FAFC` (Studio White) / `#2563EB` (Blue) |
| **09** | [`09_anime_cyber_action.yaml`](specs/09_anime_cyber_action.yaml) | Dynamic Anime Motion / Cyber-Action Graphic Novel | `#050505` (Ink Black) / `#FF0033` (Crimson) |

---
## 🎨 Asset Attribution & Recommended Fonts

These specifications reference open-source typography and audio styles. When building production assets or selecting web fonts for downstream rendering, we recommend obtaining licenses via official distributors:

* **Monospaced / Tech Fonts:** [JetBrains Mono](https://www.jetbrains.com/lp/mono/) (OFL), [Fira Code](https://github.com/tonsky/FiraCode) (OFL), [Space Mono](https://fonts.google.com/specimen/Space+Mono) (OFL).
* **Sans & Display Fonts:** [Inter](https://rsms.me/inter/) (OFL), [Cinzel](https://fonts.google.com/specimen/Cinzel) (OFL), [Orbitron](https://fonts.google.com/specimen/Orbitron) (OFL).
* **Audio & Atmosphere:** All audio directives refer to general synthesizer archetypes and Foley ambient textures. Check royalty-free audio platforms like [Freesound](https://freesound.org/) or [Mixkit](https://mixkit.co/) under creative commons.

---

## 📌 Citation & Reuse Protocol

If you use these specifications in academic research, video production workflows, or generative AI benchmarking, please cite this repository as follows:

```bibtex
@misc{notebooklm_cinematic_suite_2026,
  author = {NotebookLM Studio Contributors},
  title = {NotebookLM Studio — Cinematic Video Specification Suite},
  year = {2026},
  publisher = {GitHub},
  journal = {GitHub Repository},
  howpublished = {\url{[https://github.com/your-username/notebooklm-cinematic-suite](https://github.com/your-username/notebooklm-cinematic-suite)}}
}

📄 License
This repository and all included YAML specifications are released under the MIT License.


---

## 3. GitHub Actions CI Validation Pipeline

Create `.github/workflows/ci.yml` to automatically lint all YAML specification files and check markdown links whenever a PR is submitted or pushed to `main`.

```yaml
name: CI & YAML Validation

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  lint-yaml:
    name: Lint YAML Specs
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x'

      - name: Install yamllint
        run: pip install yamllint

      - name: Validate YAML Files
        run: |
          yamllint -d "{extends: relaxed, rules: {line-length: disable}}" specs/*.yaml

  check-links:
    name: Validate Markdown Links
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4

      - name: Link Checker
        uses: lycheeverse/lychee-action@v1
        with:
          args: --verbose --no-progress README.md docs/*.md
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
