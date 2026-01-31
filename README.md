# Machine Learning-based Force Fields (WIP)

This project is a work-in-progress, notebook-first implementation of a classic workflow for building a **machine-learning force field / potential energy surface** for a small molecular system: **alanine dipeptide in implicit solvent**.

The notebook adapts an existing tutorial as a reference.

---

## Project idea

The main goal is to demonstrate an end-to-end pipeline:

1. **Construct the system** (alanine dipeptide, implicit solvent setup). 
2. **Run biased MD** using a classical force field (ff14SBonlysc) to generate diverse configurations (sampling enhanced with metadynamics).  
3. **Label configurations** with a more expensive reference method (semi-empirical **PM6**) by computing energies and atomic forces.
4. **Fit an ML surrogate** to the PM6 energy/force surface using:
   - Gaussian Process Regression (GPR)
   - Neural Networks (NN)  
5. **Run MD on the ML potential**.  
6. **Compute free energy surfaces** (Ramachandran plot) from ML-driven sampling. 

---

## What’s currently in the notebook

- Intro + workflow outline
- Background material (e.g., brief GPR explanation) 
- Tooling choices:
  - AmberTools (ff14SBonlysc + PM6)   
  - ASE for MD + trajectory analysis  
  - nglview for interactive visualization  
  - PyTorch for autodiff + ML models  
- Environment setup notes (conda-based, mentions `environment.yml`)  

> Note: Paths and some parts of the pipeline are still being cleaned up / made reproducible.

---

## Repository structure (suggested)

As the project matures, a structure like this keeps it clean:

