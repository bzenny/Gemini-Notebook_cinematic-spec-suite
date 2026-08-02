# Contributing to NotebookLM Studio Specification Suite

Thank you for your interest in expanding our director-level prompt engine!

## How to Submit a New Genre Specification

1. **Fork the Repository** and create a feature branch (`git checkout -b feature/new-genre-spec`).
2. **Follow the 5-Layer Schema:** Every new spec must contain all 5 layers:
   - `Global Visual Settings`
   - `Typography System`
   - `Camera & Pace Settings`
   - `Audio & Soundscape`
   - `Shot Catalog (Archetypes)` (minimum 4 distinct layouts).
3. **Validate YAML Syntax:** Ensure your spec passes local validation before opening a PR:
   ```bash
   pip install yamllint
   yamllint specs/your_new_spec.yaml
Name Convention: Save new specs under specs/XX_genre_name.yaml using zero-padded numbers.

Submit a Pull Request with a detailed description of the genre, reference films/aesthetics, and color contrast tests.


### B. `CODE_OF_CONDUCT.md`
Create `CODE_OF_CONDUCT.md` in the root directory (Contributor Covenant 2.1 standard):

```markdown
# Contributor Covenant Code of Conduct

## Our Pledge
We as members, contributors, and leaders pledge to make participation in our community a harassment-free experience for everyone, regardless of age, body size, visible or invisible disability, ethnicity, sex characteristics, gender identity and expression, level of experience, education, socio-economic status, nationality, personal appearance, race, caste, color, religion, or sexual identity and orientation.

## Our Standards
Examples of behavior that contributes to a positive environment for our community include:
* Demonstrating empathy and kindness toward other people
* Being respectful of differing opinions, viewpoints, and experiences
* Giving and gracefully accepting constructive feedback
* Accepting responsibility and apologizing to those affected by our mistakes

For full guidelines or to report unacceptable behavior, contact the repository maint
