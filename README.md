
# Steady-State Thermal Analysis of a Heated Sphere

**Tools:** ANSYS Mechanical, MATLAB  
**Methods:** Thermal Finite Element Analysis (FEA), Analytical Heat Transfer, Numerical Validation

## Project Overview

This project investigates steady-state heat conduction in a solid sphere subjected to uniform internal volumetric heat generation and heat transfer at its outer surface. The objective was to determine the temperature distribution throughout the sphere and evaluate the accuracy of numerical finite element solutions by comparing them against an analytical solution.

A one-eighth symmetry model of the sphere was analyzed in ANSYS Mechanical. MATLAB was used to calculate the analytical temperature distribution and implement an independent one-dimensional finite element solution.

The project demonstrates the application of heat transfer theory, symmetry-based geometry reduction, finite element modeling, and numerical validation.

## Engineering Problem

A solid sphere generates thermal energy internally while transferring heat to its surroundings. This produces a radial temperature gradient, with the temperature varying between the center and the outer surface.

The analysis addresses the following questions:

- How does internal heat generation affect the temperature distribution?
- How accurately does ANSYS reproduce the analytical temperature profile?
- How does a one-dimensional finite element approximation compare with the analytical and ANSYS solutions?

### Model Parameters

| Parameter | Description |
|---|---|
| Geometry | Solid sphere |
| Model domain | One-eighth sphere for ANSYS |
| Analysis type | Steady-state thermal |
| Heat source | Uniform volumetric heat generation |
| Material properties | [Insert material and thermal conductivity] |
| Surface boundary condition | [Insert actual boundary condition] |
| Ambient temperature | [Insert actual ambient temperature] |

## Methodology

### 1. Analytical Solution — MATLAB

Derived the analytical temperature distribution using the governing spherical heat conduction equation and the appropriate boundary conditions.

For steady-state conduction with uniform volumetric heat generation, the governing equation is

\[
\frac{1}{r^2}\frac{d}{dr}\left(r^2 k\frac{dT}{dr}\right)+g=0
\]

where:

- \(r\) is the radial coordinate
- \(T\) is temperature
- \(k\) is thermal conductivity
- \(g\) is the volumetric heat-generation rate

The solution was obtained using zero heat flux at the sphere's center and the specified thermal boundary condition at the outer surface.

### 2. Three-Dimensional Thermal FEA — ANSYS Mechanical

Created a one-eighth solid model of the sphere to reduce computational requirements while preserving the thermal behavior of the full sphere.

Applied the material properties, internal heat generation, symmetry boundary conditions, and outer-surface thermal boundary condition. Extracted the temperature distribution along a radial path from the center to the outer surface.

### 3. One-Dimensional Finite Element Model — MATLAB

Implemented an independent one-dimensional heat conduction finite element model using five two-node elements.

Assembled the global stiffness matrix and forcing vector, solved for the nodal temperatures, and compared the resulting solution against the analytical temperature profile and ANSYS results.

## Results and Validation

The analysis produced a radial temperature distribution that could be evaluated using three approaches:

- Analytical solution
- Three-dimensional ANSYS thermal FEA
- One-dimensional MATLAB finite element solution

### ANSYS Temperature Results

| Location | Temperature |
|---|---:|
| Core | 407.67 K |
| Outer surface | 392.06 K |
| Temperature difference | 15.61 K |

The results show a temperature decrease from the center toward the outer surface. The analytical and numerical temperature profiles were compared to evaluate agreement between the models.

### Temperature Distribution Comparison

<!-- Replace with the path to your actual comparison plot. -->
![Analytical and finite element temperature comparison](Results/temperature_comparison.png)

### ANSYS Temperature Contour

<!-- Replace with the path to your actual ANSYS contour image. -->
![ANSYS temperature contour of the one-eighth sphere](Results/temperature_contour.png)

## Aerospace Engineering Relevance

Although this model represents a simplified heated sphere rather than a complete atmospheric re-entry vehicle, it demonstrates thermal analysis techniques relevant to aerospace engineering.

Understanding internal heat conduction, surface heat transfer, temperature gradients, and numerical model validation is important when evaluating thermal loads in aerospace structures and thermal protection systems.

The model does not directly simulate hypersonic flow, aerodynamic heating, ablation, or transient re-entry conditions. Its aerospace relevance lies in the underlying thermal modeling and validation methods.

## Project Files

- `MATLAB/` — Analytical solution, one-dimensional FEA implementation, and plotting scripts.
- `ANSYS/` — ANSYS model files and associated analysis results.
- `Results/` — Temperature comparison plots and ANSYS contour plots.
- `Documentation/` — Supporting derivations, assumptions, and calculations.

*Folder names and file paths should be adjusted to match the contents of this repository.*

## Key Skills Demonstrated

- Thermal finite element analysis using ANSYS Mechanical
- Analytical heat transfer and boundary-condition formulation
- One-dimensional finite element implementation in MATLAB
- Symmetry-based model reduction
- Temperature field visualization and post-processing
- Numerical solution verification and validation
- Engineering interpretation of thermal gradients
