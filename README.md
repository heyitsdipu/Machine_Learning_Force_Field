# Machine Learning-based Force Fields (WIP)

This project is a work-in-progress, notebook-first implementation of a classic workflow for building a **machine-learning force field / potential energy surface** for a small molecular system: **alanine dipeptide in implicit solvent**. :contentReference[oaicite:1]{index=1}

The notebook follows (and adapts) an existing tutorial as a reference. :contentReference[oaicite:2]{index=2}

---

## Project idea

The main goal is to demonstrate an end-to-end pipeline:

1. **Construct the system** (alanine dipeptide, implicit solvent setup). :contentReference[oaicite:3]{index=3}  
2. **Run biased MD** using a classical force field (ff14SBonlysc) to generate diverse configurations (sampling enhanced with metadynamics). :contentReference[oaicite:4]{index=4}  
3. **Label configurations** with a more expensive reference method (semi-empirical **PM6**) by computing energies and atomic forces. :contentReference[oaicite:5]{index=5}  
4. **Fit an ML surrogate** to the PM6 energy/force surface using:
   - Gaussian Process Regression (GPR)
   - Neural Networks (NN) :contentReference[oaicite:6]{index=6}  
5. **Run MD on the ML potential**. :contentReference[oaicite:7]{index=7}  
6. **Compute free energy surfaces** (Ramachandran plot) from ML-driven sampling. :contentReference[oaicite:8]{index=8}  

---

## What’s currently in the notebook

- Intro + workflow outline :contentReference[oaicite:9]{index=9}  
- Background material (e.g., brief GPR explanation) :contentReference[oaicite:10]{index=10}  
- Tooling choices:
  - AmberTools (ff14SBonlysc + PM6) :contentReference[oaicite:11]{index=11}  
  - ASE for MD + trajectory analysis :contentReference[oaicite:12]{index=12}  
  - nglview for interactive visualization :contentReference[oaicite:13]{index=13}  
  - PyTorch for autodiff + ML models :contentReference[oaicite:14]{index=14}  
- Environment setup notes (conda-based, mentions `environment.yml`) :contentReference[oaicite:15]{index=15}  

> Note: Paths and some parts of the pipeline are still being cleaned up / made reproducible.

---

## Repository structure (suggested)

As the project matures, a structure like this keeps it clean:

